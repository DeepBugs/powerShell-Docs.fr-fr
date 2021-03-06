---
title: Raccourcis clavier pour Windows PowerShell ISE
ms.date: 2016-05-11
keywords: powershell,applet de commande
description: 
ms.topic: article
author: jpjofre
manager: dongill
ms.prod: powershell
ms.assetid: 8328b946-0f02-4ef4-ac28-2743a1b4043b
translationtype: Human Translation
ms.sourcegitcommit: 466b7169b81d773cc226adbf853b46fdb956c2f1
ms.openlocfilehash: 852b927ba0f5edffa5c7943b45e0e7b1bdd273f5

---

# Raccourcis clavier pour Windows PowerShell ISE
Pour effectuer des actions dans l’environnement d’écriture de scripts intégré de Windows PowerShell®, utilisez les raccourcis clavier suivants. Windows PowerShell ISE est intégré aux systèmes d’exploitation Windows Server et Windows Client, mais peut également être installé sur certains systèmes d’exploitation Windows plus anciens comme composant du [package de téléchargement de Windows Management Framework 4.0](http://go.microsoft.com/fwlink/?LinkID=293881).

## Raccourcis clavier pour l’édition de texte
Lorsque vous éditez un texte, vous pouvez utiliser les raccourcis clavier suivants.

|Action|Raccourcis clavier|Utiliser dans|
|----------|----------------------|----------|
|**Aide**|F1|Volet Script **Important :** vous pouvez spécifier que la touche F1 provient de la Bibliothèque TechNet sur le web ou de l’aide téléchargée (voir Update-Help). Pour opérer votre choix, cliquez sur **Outils**, **Options**, sur l’onglet **Paramètres généraux**, puis activez ou désactivez l’option **Utiliser le contenu de l’aide locale au lieu du contenu en ligne.**|
|**Copier**|Ctrl+C|Volets Script, Commande et Sortie|
|**Couper**|Ctrl+X|Volets Script et Commande|
|**Développer ou réduire le plan**|Ctrl+M|Volet Script|
|**Rechercher dans le script**|Ctrl+F|Volet Script|
|**Rechercher suivant dans le script**|F3|Volet Script|
|**Rechercher précédent dans le script**|Maj+F3|Volet Script|
|**Rechercher l’accolade correspondante**|Ctrl+]|Volet Script|
|**Coller**|Ctrl+V|Volets Script et Commande|
|**Rétablir**|Ctrl+Y|Volets Script et Commande|
|**Remplacer dans le script**|Ctrl+H|Volet Script|
|**Enregistrer**|Ctrl+S|Volet Script|
|**Sélectionner tout**|Ctrl+A|Volets Script, Commande et Sortie|
|**Afficher les extraits de code**|CTRL+J|Volets Script et Commande|
|**Annuler**|Ctrl+Z|Volets Script et Commande|

## Raccourcis clavier pour exécuter les scripts
Lorsque vous exécutez des scripts dans le volet Script, vous pouvez utiliser les raccourcis clavier suivants.

|Action|Raccourci clavier|
|----------|---------------------|
|**Nouveau**|Ctrl+N|
|**Ouvrir**|Ctrl+O|
|**Exécuter**|F5|
|**Exécuter la sélection**|F8|
|**Arrêter l’exécution**|CTRL+PAUSE. Vous pouvez utiliser Ctrl+C quand le contexte est sans ambiguïté (quand aucun texte n’est sélectionné).|
|**Tab** (pour accéder au script suivant)|Ctrl+Tab **Remarque :** L’usage de la touche Tab pour accéder au script suivant fonctionne uniquement quand un seul onglet Windows PowerShell est ouvert ou, si plusieurs onglets Windows PowerShell sont ouverts, quand le focus est dans le volet Script.|
|**Tab** (pour accéder au script précédent)|Ctrl+Maj+Tab **Remarque :** L’usage de la touche Tab pour accéder au script précédent fonctionne uniquement quand un seul onglet Windows PowerShell est ouvert ou, si plusieurs onglets Windows PowerShell sont ouverts, quand le focus est dans le volet Script.|

## Raccourcis clavier pour la personnalisation de l’affichage
Pour personnaliser l’affichage dans Windows PowerShell ISE, vous pouvez utiliser les raccourcis clavier suivants. Ils sont accessibles à partir de tous les volets de l’application.

|Action|Raccourci clavier|
|----------|---------------------|
|**Accédez au volet Commande (v2) ou Console (v3 et versions ultérieures)**|Ctrl+D|
|**Accéder au volet Sortie (v2 uniquement)**|Ctrl+Maj+ O|
|**Accéder au volet Script**|Ctrl+I|
|**Afficher le volet Script**|Ctrl+R|
|**Masquer le volet Script**|Ctrl+R|
|**Déplacer le volet Script vers le haut**|Ctrl+1|
|**Déplacer le volet Script vers la droite**|Ctrl+2|
|**Maximiser le volet Script**|Ctrl+3|
|**Zoom avant**|Ctrl+Signe Plus|
|**Zoom arrière**|Ctrl+Signe Moins|

## Raccourcis clavier pour le débogage des scripts
Lors du débogage de scripts, vous pouvez utiliser les raccourcis clavier suivants.

|Action|Raccourci clavier|Utiliser dans|
|----------|---------------------|----------|
|**Exécuter/continuer**|F5|Volet Script, lors du débogage d’un script|
|**Pas à pas détaillé**|F11|Volet Script, lors du débogage d’un script|
|**Pas à pas principal**|F10|Volet Script, lors du débogage d’un script|
|**Pas à pas sortant**|Maj+F11|Volet Script, lors du débogage d’un script|
|**Afficher la pile des appels**|Ctrl+Maj+D|Volet Script, lors du débogage d’un script|
|**Afficher la liste des points d’arrêt**|Ctrl+Maj+L|Volet Script, lors du débogage d’un script|
|**Basculer le point d’arrêt**|F9|Volet Script, lors du débogage d’un script|
|**Supprimer tous les points d’arrêt**|Ctrl+Maj+F9|Volet Script, lors du débogage d’un script|
|**Arrêter le débogueur**|Maj+F5|Volet Script, lors du débogage d’un script|

> [!NOTE]
> Lors du débogage de scripts dans Windows PowerShell ISE, vous pouvez également utiliser les raccourcis clavier conçus pour la console Windows PowerShell. Pour utiliser ces raccourcis, vous devez les taper dans le volet Commande, puis appuyer sur Entrée.

|Action|Raccourci clavier|Utiliser dans|
|----------|---------------------|----------|
|**Continuer**|C|Volet Console, lors du débogage d’un script|
|**Pas à pas détaillé**|S|Volet Console, lors du débogage d’un script|
|**Pas à pas principal**|V|Volet Console, lors du débogage d’un script|
|**Pas à pas sortant**|O|Volet Console, lors du débogage d’un script|
|**Répéter la dernière commande** (pour un pas à pas détaillé ou un pas à pas principal)|ENTRÉE|Volet Console, lors du débogage d’un script|
|**Afficher la pile des appels**|K|Volet Console, lors du débogage d’un script|
|**Arrêter le débogage**|Q|Volet Console, lors du débogage d’un script|
|**Afficher le script**|L|Volet Console, lors du débogage d’un script|
|**Afficher les commandes de débogage de la console**|H ou ?|Volet Console, lors du débogage d’un script|

## Raccourcis clavier pour les onglets Windows PowerShell
Lorsque vous utilisez les onglets Windows PowerShell, vous pouvez utiliser les raccourcis clavier suivants.

|Action|Raccourci clavier|
|----------|---------------------|
|**Fermer l’onglet PowerShell**|Ctrl+W|
|**Nouvel onglet PowerShell**|CTRL+T|
|**Onglet PowerShell précédent**|Ctrl+Maj+Tab Ce raccourci ne fonctionne que si aucun fichier n’est ouvert sous aucun onglet Windows PowerShell.|
|**Onglet Windows PowerShell suivant**|CTRL+Tab Ce raccourci ne fonctionne que si aucun fichier n’est ouvert sous aucun onglet Windows PowerShell.|

## Raccourcis clavier pour le démarrage et la fermeture
Pour démarrer la console Windows PowerShell (PowerShell.exe) ou pour quitter Windows PowerShell ISE, vous pouvez utiliser les raccourcis clavier suivants.

|Action|Raccourci clavier|
|----------|---------------------|
|**Quitter**|ALT+F4|
|**Démarrer PowerShell.exe** (console Windows PowerShell)|Ctrl+Maj+P|

## Voir aussi
[PowerShell Magazine : Liste complète des raccourcis clavier pour Windows PowerShell ISE](http://www.powershellmagazine.com/2013/01/29/the-complete-list-of-powershell-ise-3-0-keyboard-shortcuts/)




<!--HONumber=Sep16_HO3-->


