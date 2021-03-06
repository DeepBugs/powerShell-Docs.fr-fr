---
title: "Améliorations du moteur PowerShell"
author: jasonsh
translationtype: Human Translation
ms.sourcegitcommit: 47c963343c541d0f2ace194f365de5fcd809ccc5
ms.openlocfilehash: 1b35a25312b44d14ec8771be9e17aaa43e270b61

---

# Améliorations du moteur PowerShell #

Les améliorations suivantes du moteur principal PowerShell ont été implémentées pour PowerShell 5.1 :


## Performances ##

Les performances ont été améliorées dans certains domaines importants :

1. Démarrage
2. Le traitement « pipeline » vers les applets de commande ForEach-Object et Where-Object est environ 50 % plus rapide. 

Voici quelques exemples d’améliorations (les résultats peuvent varier en fonction de votre matériel) : 

| Scénario | Durée 5.0 (ms) | Durée 5.1 (ms) |
| -------- | :---------------: | :---------------: |
| `powershell -command "echo 1"` | 900 | 250 |
| Première exécution PowerShell : `powershell -command "Unknown-Command"` | 30 000 | 13 000 |
| Création du cache d’analyse de commande : `powershell -command "Unknown-Command"` | 7000 | 520 |
| <code>1..1000000 &#124; % { }</code> | 1400 | 750 |
  
Une modification liée au démarrage peut affecter certains scénarios (non pris en charge). PowerShell ne lit plus les fichiers `$pshome\*.ps1xml`. Ces fichiers ont été convertis en C# pour éviter une surcharge du processeur et des fichiers lors du traitement des fichiers XML. Les fichiers existent toujours pour prendre en charge V2 côte à côte. Ainsi, si vous modifiez le contenu des fichiers, cela n’affecte pas V5 mais uniquement V2. Notez que la modification du contenu de ces fichiers n’a jamais été un scénario pris en charge.

Une autre modification visible est la façon dont PowerShell met en cache les commandes exportées et d’autres informations pour les modules installés sur un système. Auparavant, ce cache était stocké dans le répertoire `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\CommandAnalysis`. Dans WMF 5.1, le cache est un fichier unique `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.
Pour plus de détails, consultez la page [analysis_cache.md]().

À compter de la version 5.1, PowerShell est disponible dans différentes éditions qui indiquent la compatibilité de la plateforme et les différents ensembles de fonctionnalités.



## Résolutions de bogues ##

Les bogues importants suivants ont été résolus :

### La détection automatique de module est honorée complètement `$env:PSModulePath` ###

La détection automatique de module (chargement automatique des modules sans Import-Module explicite lors de l’appel d’une commande) a été introduite dans WMF3. Lors de l’introduction, PowerShell vérifiait la présence des commandes dans `$PSHome\Modules` avant d’utiliser `$env:PSModulePath`.

WMF 5.1 modifie ce comportement pour honorer `$env:PSModulePath` complètement. Ainsi, un module créé par l’utilisateur qui définit des commandes fournies par PowerShell (par exemple, `Get-ChildItem`) peut être chargé automatiquement et remplacer correctement la commande intégrée.

### La redirection de fichiers ne code plus en dur `-Encoding Unicode` ###

Dans toutes les versions précédentes de PowerShell, il était impossible de contrôler l’encodage de fichier utilisé par l’opérateur de redirection de fichier, par exemple `Get-ChildItem > out.txt`, car PowerShell ajoutait `-Encoding Unicode`.

À compter de WMF 5.1, vous pouvez modifier l’encodage de fichier de la redirection en définissant `$PSDefaultParameterValues`, par exemple

```
$PSDefaultParameterValues["Out-File:Encoding"] = "Ascii"
```

### Correction d’une régression dans l’accès aux membres de `System.Reflection.TypeInfo` ###

Une régression introduite dans WMF 5 interrompait l’accès aux membres de `System.Reflection.RuntimeType`, par exemple `[int].ImplementedInterfaces`.
Ce bogue a été résolu dans WMF 5.1.


### Résolution de certains problèmes liés aux objets COM ###

WMF 5 a introduit un nouveau binder COM pour appeler des méthodes sur des objets COM et accéder aux propriétés des objets COM.
Ce nouveau binder a amélioré les performances de manière significative, mais il a également introduit des bogues qui ont été résolus dans WMF 5.1.

#### Les conversions d’arguments n’étaient pas toujours effectuées correctement ####

Dans l’exemple suivant :

```
$obj = New-Object -ComObject WScript.Shell
$obj.SendKeys([char]173)
```

La méthode SendKeys attend une chaîne, mais PowerShell n’a pas converti le caractère en chaîne, ce qui diffère la conversion en IDispatch::Invoke, qui utilise VariantChangeType pour effectuer la conversion. Dans cet exemple, cela provoque l’envoi des clés « 1 », « 7 » et « 3 » au lieu de la clé Volume.Mute attendue.

#### Les objets COM énumérables ne sont pas toujours gérés correctement ####

PowerShell énumère normalement la plupart des objets énumérables, mais une régression introduite dans WMF 5 empêchait l’énumération des objets COM qui implémentent IEnumerable.  Par exemple :

```
function Get-COMDictionary
{
    $d = New-Object -ComObject Scripting.Dictionary
    $d.Add('a', 2)
    $d.Add('b', 2)
    return $d
}

$x = Get-COMDictionary
```

Dans l’exemple ci-dessus, WMF 5 écrivait incorrectement le Scripting.Dictionary dans le pipeline au lieu d’énumérer les paires clé/valeur.


### `[ordered]` n’était pas autorisé à l’intérieur des classes ###

WMF 5 a introduit des classes avec la validation des littéraux de type utilisée dans les classes.  `[ordered]` ressemble à un littéral de type, mais ce n’est pas un vrai type .NET.  WMF 5 signalait incorrectement une erreur sur `[ordered]` à l’intérieur d’une classe :

```
class CThing
{
    [object] foo($i)
    {
        [ordered]@{ Thing = $i }
    }
}
```


### L’aide sur les rubriques de procédures avec plusieurs versions ne fonctionne pas ###

Avant WMF 5.1, si plusieurs versions d’un module étaient installées et que toutes partageaient une rubrique d’aide, par exemple about_PSReadline, `help about_PSReadline` retournait plusieurs rubriques sans aucun moyen évident d’afficher l’aide réelle.

WMF 5.1 résout ce problème en retournant l’aide de la version la plus récente de la rubrique.

Get-Help n’offre aucun moyen de spécifier la version pour laquelle vous souhaitez obtenir de l’aide. La solution de contournement consiste à accéder au répertoire de modules et d’afficher l’aide directement avec un outil tel que votre éditeur favori. 



<!--HONumber=Sep16_HO3-->


