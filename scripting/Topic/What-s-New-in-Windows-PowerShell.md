---
title: Nouveautés dans Windows PowerShell 39
ms.custom: na
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 1476722e-947e-425d-a86c-50037488dc6e
---
# Nouveautés dans Windows PowerShell 39
[!INCLUDE[wps_1](../Token/wps_1_md.md)] 5.0 intègre plusieurs nouvelles fonctionnalités importantes qui, en plus d’étendre et de simplifier son utilisation, vous permettent de contrôler et de gérer des environnements Windows plus aisément et de façon plus poussée.

[!INCLUDE[wps_2](../Token/wps_2_md.md)] 5.0 offre une compatibilité descendante. Les applets de commande, fournisseurs, modules, composants logiciels enfichables, scripts, fonctions et profils conçus pour [!INCLUDE[psversion4](../Token/psversion4_md.md)], [!INCLUDE[psversion3](../Token/psversion3_md.md)] et [!INCLUDE[psversion2](../Token/psversion2_md.md)] fonctionnent généralement dans [!INCLUDE[wps_2](../Token/wps_2_md.md)] 5.0 sans qu’une modification soit nécessaire.

[!INCLUDE[wps_2](../Token/wps_2_md.md)] 5.0 est installé par défaut sous [!INCLUDE[winthreshold_server_1](../Token/winthreshold_server_1_md.md)] et [!INCLUDE[winthreshold_client_1](../Token/winthreshold_client_1_md.md)]. Pour installer [!INCLUDE[wps_2](../Token/wps_2_md.md)] 5.0 sur [!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)], [!INCLUDE[winblue_client_ent_2](../Token/winblue_client_ent_2_md.md)] ou [!INCLUDE[winblue_client_pro_2](../Token/winblue_client_pro_2_md.md)], téléchargez et installez [Windows Management Framework 5.0 Preview](http://go.microsoft.com/fwlink/?LinkID=395058). Avant d’installer Windows Management Framework 5.0 Preview, veillez à prendre connaissance des détails du téléchargement et à vérifier entièrement la configuration requise.

## Dans cette rubrique

-   [Mises à jour de la DSC de Windows PowerShell 4.0 dans la base de connaissances 3000850](#BKMK_3000850)

-   [Nouvelles fonctionnalités dans Windows PowerShell 5.0](#BKMK_new50)

-   [Nouvelles fonctionnalités dans Windows PowerShell 4.0](#BKMK_wps4)

-   [Nouvelles fonctionnalités dans Windows PowerShell 3.0](#BKMK_wps3)

## <a name="BKMK_3000850"></a>Mises à jour de Windows PowerShell 4.0 dans le correctif cumulatif de novembre 2014 (3000850 Ko)
Plusieurs mises à jour et améliorations de la [!INCLUDE[wps_2](../Token/wps_2_md.md)] configuration d’état souhaité (DSC) dans [!INCLUDE[wps_2](../Token/wps_2_md.md)] 4.0 sont disponibles dans le [correctif cumulatif de novembre 2014 pour Windows RT 8.1, Windows 8.1 et Windows Server 2012 R2](https://support.microsoft.com/kb/3000850/) (KB 3000850). Pour déterminer si KB 3000850 est installé sur votre système, exécutez `Get-Hotfix -Id KB3000850` dans [!INCLUDE[wps_2](../Token/wps_2_md.md)].

-   Mises à jour des applets de commande existantes dans le module [PSDesiredStateConfiguration](https://technet.microsoft.com/library/dn391651(v=wps.640).aspx)

    -   [Get-DscResource](http://technet.microsoft.com/library/dn521625.aspx) : plus rapide (en particulier dans ISE).

    -   [Start-DscConfiguration](http://technet.microsoft.com/library/dn521623.aspx) : un nouveau paramètre, -UseExisting, réapplique la dernière configuration appliquée.

    -   [Start-DscConfiguration](http://technet.microsoft.com/library/dn521623.aspx) : le paramètre -Force a été corrigé.

    -   [Get-DscLocalConfigurationManager](http://technet.microsoft.com/library/dn407378.aspx): affiche davantage d’informations utiles sur l’état du moteur.

    -   [Test-DscConfiguration](http://technet.microsoft.com/library/dn407382.aspx) : désormais le nom de l’ordinateur avec la valeur True ou False.

    -   [Nouveau-DscChecksum](http://technet.microsoft.com/library/dn521622.aspx) : prend désormais en charge les chemins d’accès UNC.

-   Nouvelles applets de commande dans le module [PSDesiredStateConfiguration](http://technet.microsoft.com/library/dn391651(v=wps.640).aspx)

    -   [Update-DscConfiguration](http://technet.microsoft.com/library/mt143541(v=wps.630).aspx) : effectue une vérification du serveur collecteur à la demande.

    -   [Stop-DscConfiguration](http://technet.microsoft.com/library/mt143542(v=wps.630).aspx) : arrête une configuration en cours d’exécution.

    -   [Remove-DscConfigurationDocument](http://technet.microsoft.com/library/mt143544(v=wps.630).aspx) : permet de supprimer des documents de configuration dans différentes phases (en attente, précédente ou actuelle).

-   Rehaussement du langage

    -   DependsOn prend désormais en charge des ressources composites.

    -   DependsOn prend désormais en charge les chiffres dans les noms d’instance de ressource.

    -   Les expressions de nœud évaluées comme vides ne déclenchent plus d’erreurs.

    -   L’erreur qui se produisait quand une expression de nœud était évaluée comme vide a été corrigée.

    -   Les configurations appelant des configurations fonctionnent désormais dans la console [!INCLUDE[wps_2](../Token/wps_2_md.md)].

-   Rehaussement du mode par extraction

    -   Le mode par extraction prend désormais en charge tous les fichiers ZIP.

    -   **AllowModuleOverwrite** fonctionne désormais correctement.

-   Améliorations apportées à la résilience

    -   Le nouveau **DebugMode** permet de recharger des modules de ressources.

    -   En cas d’erreur de configuration, le fichier pending.mof n’est plus supprimé.

    -   Le gestionnaire de configuration local (LCM) est désormais plus résilient en cas d’endommagement des paramètres de métaconfiguration.

-   Améliorations apportées au diagnostic

    -   Un avertissement s’affiche lorsque le LCM modifie les paramètres que vous avez définis pour le minuteur.

    -   Les fichiers journaux des erreurs contiennent désormais la pile des appels pour les ressources [!INCLUDE[wps_2](../Token/wps_2_md.md)].

-   Améliorations apportées à l’extensibilité

    -   La ressource LocalConfigurationManager a une nouvelle propriété, **ActionAfterReboot**.

        -   ContinueConfiguration (valeur par défaut) : reprend automatiquement une configuration après le redémarrage d’un nœud cible.

        -   StopConfiguration : ne reprend pas automatiquement une configuration après le redémarrage d’un nœud.

    -   Une série de tests de cohérence peut désormais se produire plus souvent qu’une opération d’extraction, ou inversement.

    -   Prise en charge du contrôle de version : la DSC peut désormais reconnaître un document généré sur un client plus récent (intégrée à [WMF 5.0 Preview](http://go.microsoft.com/fwlink/?LinkID=395058)).

-   Améliorations apportées à la prévention des erreurs

    -   La version de module est désormais appliquée avant une configuration.

    -   La variable **DebugPreference** est désormais définie correctement pour les appels Get-TargetResource, Set-TargetResource et Test-TargetResource.

-   Améliorations apportées à la gestion des informations d’identification

    -   Un certificat est désormais utilisé, si **Certificate** et **PSDscAllowPlainTextPassword** sont spécifiés.

    -   Les informations d’identification sont déchiffrées, même pour les appels Get-TargetResource.

    -   Les informations d’identification de métaconfiguration sont chiffrées et déchiffrées.

    -   Les PSCredentials sont désormais déchiffrées quand elles figurent dans un objet incorporé.

-   Améliorations apportées aux ressources intégrées

    -   Package resource

        -   N’installe plus le package incorrect (à partir de sources locales ou web).

        -   Prend désormais en charge le protocole HTTPS.

    -   [Package resource](http://technet.microsoft.com/library/dn282132.aspx) prend désormais en charge le protocole HTTPS.

    -   [Archive resource](http://technet.microsoft.com/library/dn249917.aspx) prend désormais en charge les informations d’identification.

## <a name="BKMK_new50"></a>Nouvelles fonctionnalités dans Windows PowerShell 5.0

-   [Nouvelles fonctionnalités dans Windows PowerShell](#BKMK_newcore)

-   [Nouvelles fonctionnalités dans la configuration d’état souhaité de Windows PowerShell](#BKMK_newDSC)

-   [Nouvelles fonctionnalités dans Windows PowerShell ISE](#BKMK_newISE)

-   [Nouvelles fonctionnalités dans Windows PowerShell Web Services](#BKMK_newOData)

-   [Correctifs de bogues notables dans Windows PowerShell 5.0](#BKMK_5bugfix)

### <a name="BKMK_newcore"></a>Nouvelles fonctionnalités dans Windows PowerShell

-   Désormais, dans [!INCLUDE[wps_2](../Token/wps_2_md.md)] 5.0, vous pouvez développer à l’aide de classes, en utilisant une syntaxe et une sémantique formelles similaires à celles d’autres langages de programmation orientée objet. Des mots clés tels que **Class** et **Enum** ont été ajoutés au langage [!INCLUDE[wps_2](../Token/wps_2_md.md)] pour prendre en charge la nouvelle fonctionnalité. Pour plus d’informations sur l’utilisation des classes, voir la rubrique les concernant.

-   [!INCLUDE[wps_2](../Token/wps_2_md.md)] 5.0 introduit un nouveau flux d’informations structurées utilisable pour échanger des données structurées entre un script et ses appelants (environnement d’hébergement). Vous pouvez désormais utiliser Write-Host pour envoyer la sortie au flux d’informations. Les flux d’informations fonctionnent également pour PowerShell.Streams, les travaux, les travaux planifiés et les flux de travail. Les fonctionnalités suivantes prennent en charge le flux d’informations.

    -   Une nouvelle applet de commande, Write-Information, permet de spécifier la manière dont [!INCLUDE[wps_2](../Token/wps_2_md.md)] gère les données de flux d’informations pour une commande. Write-Host est un wrapper pour Write-Information. Write-Information est également une activité de flux de travail prise en charge.

    -   Deux nouveaux paramètres courants, InformationVariable et InformationAction, permettent de déterminer le mode d’affichage des flux d’informations en provenance d’une commande. Les valeurs valides pour InformationAction sont SilentlyContinue, Stop, Continue, Inquire, Ignore ou Suspend, Continue étant la valeur par défaut. InformationVariable spécifie une chaîne en tant que nom d’une variable dans laquelle vous souhaitez enregistrer les données Write-Host en provenance d’une commande.

    -   Une nouvelle variable de préférence, InformationPreference, spécifie votre préférence par défaut pour les données du flux d’informations dans une session [!INCLUDE[wps_2](../Token/wps_2_md.md)]. La valeur par défaut est Continue.

    -   Deux nouveaux paramètres communs de flux de travail, PSInformation et InformationAction, ont été ajoutés.

    -   Lorsque vous utilisez la commande Format-Table, les colonnes de table sont désormais mises en forme automatiquement en évaluant les 300 premières millisecondes de données qui transitent dans le flux.

-   En collaboration avec [Microsoft Research](http://research.microsoft.com/), une nouvelle applet de commande, ConvertFrom-String, a été ajoutée. L’applet de commande ConvertFrom-String permet d’extraire des objets structurés du contenu de chaînes de texte, et de les analyser. Pour plus d’informations, voir ConvertFrom-String.

-   Une nouvelle applet de commande, Convert-String, met en forme automatiquement le texte sur la base d’un exemple que vous fournissez dans un paramètre -Example.

-   Un nouveau module, Microsoft.PowerShell.Archive, inclut des applets de commande qui vous permettent de compresser des fichiers et dossiers dans des fichiers d’archives (également appelés ZIP), d’extraire des fichiers de fichiers ZIP, et de mettre à jour des fichiers ZIP avec des versions plus récentes des fichiers qui y sont compressés.

-   Un nouveau module, PackageManagement, permet de détecter des packages logiciels sur Internet, et de les installer. Le module PackageManagement (anciennement OneGet) est un gestionnaire ou multiplexeur de gestionnaires de package existants (également appelés fournisseurs du package), destiné à unifier la gestion des packages Windows avec une seule interface Windows PowerShell.

-   Un nouveau module, PowerShellGet, permet de rechercher, d’installer, de publier et de mettre à jour des modules et des ressources DSC dans la [Galerie PowerShell](http://www.powershellgallery.com/), ou dans un référentiel de module interne que vous pouvez configurer en exécutant l’applet de commande Register-PSRepository.

-   Un nouveau mot clé du langage, **Hidden**, a été ajouté pour spécifier qu’un membre (une propriété ou une méthode) n’est pas affiché par défaut dans les résultats de l’applet de commande Get-Member (sauf si vous ajoutez le paramètre -Force). Les propriétés ou méthodes marquées pour être masquées n’apparaissent pas non plus dans les résultats d’IntelliSense, sauf si vous êtes dans un contexte où le membre doit être visible. Par exemple, la variable automatique $This doit afficher les membres masqués dans le contexte de la méthode Class.

-   Les applets de commande New-Item, Remove-Item et Get-ChildItem ont été rehaussées pour prendre en charge la création et la gestion des [liens symboliques](http://en.wikipedia.org/wiki/Symbolic_link). Le paramètre **ItemType** de l’applet de commande New-Item accepte une nouvelle valeur, **SymbolicLink**. Vous pouvez désormais créer des liens symboliques en une seule ligne, en exécutant l’applet de commande New-Item.

-   L’applet de commande Get-ChildItem dispose également d’un nouveau paramètre, -Depth, que vous pouvez utiliser avec le paramètre Recurse pour limiter la récursivité. Par exemple, la commande Get-ChildItem -Recurse -Depth 2 retourne des résultats à partir du dossier actif, de tous les dossiers enfants de ce dossier, et de tous les sous-dossiers des dossiers enfants.

-   L’applet de commande Copy-Item permet désormais de copier des fichiers ou dossiers d’une session [!INCLUDE[wps_2](../Token/wps_2_md.md)] vers une autre. Vous pouvez ainsi copier des fichiers vers des sessions connectées à des ordinateurs distants (y compris des ordinateurs exécutant [Windows Nano Server](http://blogs.technet.com/b/windowsserver/archive/2015/04/08/microsoft-announces-nano-server-for-modern-apps-and-cloud.aspx), qui n’ont donc pas d’autre interface). Pour copier des fichiers, spécifiez des ID PSSession comme valeurs pour les nouveaux paramètres -ToSession et -FromSession, en ajoutant -Path et -Destination pour spécifier respectivement le chemin d’accès d’origine et la destination. Par exemple, Copy-Item -Path c:\myFile.txt -ToSession $s -Destination d:\destinationFolder.

-   La transcription [!INCLUDE[wps_2](../Token/wps_2_md.md)] a été améliorée pour s’appliquer à toutes les applications d’hébergement (telles que [!INCLUDE[wps_2](../Token/wps_2_md.md)]ISE) en plus de l’hôte de la console (**powershell.exe**). Vous pouvez configurer des options de transcription (notamment la transcription à l’échelle du système) en activant le paramètre de stratégie de groupe **Activer la transcription PowerShell** accessible dans Modèles d’administration/Composants Windows/[!INCLUDE[wps_2](../Token/wps_2_md.md)].

-   Une nouvelle fonctionnalité de suivi de script détaillé permet d’activer le suivi et l’analyse de l’utilisation des scripts [!INCLUDE[wps_2](../Token/wps_2_md.md)] sur un système. Après avoir activé le suivi de script détaillé, [!INCLUDE[wps_2](../Token/wps_2_md.md)] journalise tous les blocs de scripts dans le journal des événements Suivi d’événements pour Windows (ETW), **Microsoft-Windows-PowerShell/Operational**.

-   Désormais, dans [!INCLUDE[wps_2](../Token/wps_2_md.md)] 5.0, de nouvelles applets de commande CMS (Cryptographic Message Syntax) prennent en charge le chiffrement et le déchiffrement de contenu à l’aide du format IETF standard pour protéger par chiffrement des messages, comme décrit dans [RFC5652](http://tools.ietf.org/html/rfc5652). Les applets de commande Get-CmsMessage, Protect-CmsMessage et Unprotect-CmsMessage ont été ajoutées au module [Microsoft.PowerShell.Security](http://technet.microsoft.com/library/hh849807.aspx).

-   Les nouvelles applets de commande du module [Microsoft.PowerShell.Utility](http://technet.microsoft.com/library/hh849958.aspx) (Get-Runspace, Debug-Runspace, Get-RunspaceDebug, Enable-RunspaceDebug et Disable-RunspaceDebug) vous permettent de définir des options de débogage ainsi que de démarrer et d’arrêter le débogage sur une instance d’exécution. Pour le débogage d’instances d’exécution arbitraires (c’est-à-dire, autres que l’instance d’exécution par défaut pour une console [!INCLUDE[wps_2](../Token/wps_2_md.md)] ou une session [!INCLUDE[wps_2](../Token/wps_2_md.md)]ISE), [!INCLUDE[wps_2](../Token/wps_2_md.md)] permet de définir des points d’arrêt dans un script, qui interrompent l’exécution de celui-ci jusqu’à ce que vous puissiez attacher un débogueur pour déboguer le script de l’instance d’exécution. Une prise en charge du débogage imbriqué pour les instances d’exécution arbitraires a été ajoutée au débogueur de script [!INCLUDE[wps_2](../Token/wps_2_md.md)] pour les instances d’exécution.

-   Une nouvelle applet de commande, Format-Hex, a été ajoutée au module [Microsoft.PowerShell.Utility](http://technet.microsoft.com/library/hh849958.aspx). L’applet de commande Format-Hex permet d’afficher du texte ou des données binaires au format hexadécimal.

-   Les applets de commande Get-Clipboard et Set-Clipboard ont été ajoutées au module [Microsoft.PowerShell.Utility](http://technet.microsoft.com/library/hh849958.aspx). Elles facilitent l’échange de contenu entre sessions [!INCLUDE[wps_2](../Token/wps_2_md.md)]. Les applets de commande du Presse-papiers prennent en charge les images, les fichiers audio, les listes de fichiers et le texte.

-   Une nouvelle applet de commande, Clear-RecycleBin, a été ajoutée au module [Microsoft.PowerShell.Management](http://technet.microsoft.com/library/hh849827(v=wps.640).aspx). Elle permet de vider la Corbeille d’un lecteur fixe, y compris s’il s’agit d’un lecteur externe. Par défaut, vous êtes invité à confirmer une commande Clear-RecycleBin, car la propriété ConfirmImpact de l’applet de commande est définie sur ConfirmImpact.High.

-   Une nouvelle applet de commande, New-TemporaryFile, permet de créer un fichier temporaire dans le cadre d’un script. Par défaut, le fichier temporaire est créé dans C:\Users\<user name>\AppData\Local\Temp.

-   Les applets de commande Out-File, Add-Content et Set-Content disposent désormais d’un nouveau paramètre, -NoNewline, qui omet toute nouvelle ligne après la sortie.

-   L’applet de commande New-Guid tire parti de la classe Guid de .NET Framework pour générer un GUID utile lorsque vous écrivez des scripts ou des ressources DSC.

-   Étant donné que les informations sur la version d’un fichier peuvent être trompeuses, en particulier après correction de celui-ci, de nouvelles propriétés de script, FileVersionRaw et ProductVersionRaw, sont disponibles pour les objets FileInfo. Par exemple, vous pouvez exécuter la commande suivante afin d’afficher les valeurs de ces propriétés pour PowerShell.exe : Get-Process -Id $pid -FileVersionInfo | Format-List *version* -Force. $pid contient l’ID de processus d’une session en cours d’exécution de Windows PowerShell.

-   Les nouvelles applets de commande Enter-PSHostProcess et Exit-PSHostProcess permettent de déboguer des scripts [!INCLUDE[wps_2](../Token/wps_2_md.md)] dans des processus distincts du processus actuel en cours d’exécution sur la console [!INCLUDE[wps_2](../Token/wps_2_md.md)]. Exécutez Enter-PSHostProcess pour entrer dans ou associer à un ID de processus spécifique, puis exécutez Get-Runspace pour retourner les instances d’exécution actives au sein du processus. Exécutez Exit-PSHostProcess pour dissocier du processus lorsque vous avez fini de déboguer le script au sein du processus.

-   Une nouvelle applet de commande, Wait-Debugger, a été ajoutée au module [Microsoft.PowerShell.Utility](http://technet.microsoft.com/library/hh849958.aspx). L’applet de commande Wait-Debugger permet d’arrêter l’exécution d’un script dans le débogueur avant d’exécuter l’instruction suivante du script.

-   Le débogueur de flux de travail de [!INCLUDE[wps_2](../Token/wps_2_md.md)] prend désormais en charge l’exécution par commande ou via la touche Tab, et vous pouvez déboguer des fonctions de flux de travail imbriquées. Vous pouvez désormais appuyer sur **Ctrl+Pause** pour activer le débogueur dans un script en cours d’exécution, dans des sessions tant locales que distantes, et dans un script de flux de travail.

-   Une applet de commande, Debug-Job, a été ajoutée au module [Microsoft.PowerShell.Core](http://technet.microsoft.com/library/hh849695.aspx). Elle permet de déboguer des scripts de travail en cours d’exécution pour le flux de travail [!INCLUDE[wps_2](../Token/wps_2_md.md)], l’arrière-plan et les travaux en cours d’exécution dans des sessions à distance.

-   Un nouvel état, AtBreakpoint, a été ajouté pour les travaux [!INCLUDE[wps_2](../Token/wps_2_md.md)]. L’état AtBreakpoint s’applique quand un travail exécute un script incluant une série de points d’arrêt, au moment où le script atteint un point d’arrêt. Quand un travail est interrompu à un point d’arrêt de débogage, vous devez déboguer le travail en exécutant l’applet de commande Debug-Job.

-   [!INCLUDE[wps_2](../Token/wps_2_md.md)]5.0 prend en charge plusieurs versions d’un module [!INCLUDE[wps_2](../Token/wps_2_md.md)] à l’intérieur du même dossier dans $PSModulePath. Une propriété, RequiredVersion, a été ajoutée à la classe ModuleSpecification pour vous aider à obtenir la version souhaitée d’un module. Cette propriété ne peut pas être utilisée en même temps que la propriété ModuleVersion. La propriété RequiredVersion est désormais prise en charge. Elle est incluse dans la valeur du paramètre FullyQualifiedName des applets de commande Get-Module, Import-Module et Remove-Module.

-   Vous pouvez désormais effectuer une validation de la version du module en exécutant l’applet de commande Test-ModuleManifest.

-   Les résultats de l’applet de commande Get-Command affichent désormais une colonne Version suite à l’ajout d’une nouvelle propriété, Version, à la classe CommandInfo. L’applet de commande Get-Command affiche les commandes de plusieurs versions du même module. La propriété Version fait également partie des classes dérivées de CmdletInfo:CmdletInfo et d’ApplicationInfo.

-   L’applet de commande Get-Command dispose d’un nouveau paramètre, -ShowCommandInfo, qui retourne les informations de ShowCommand en tant que PSObjects. Cette fonctionnalité est particulièrement utile lors de l’exécution de l’applet de commande Show-Command dans [!INCLUDE[wps_2](../Token/wps_2_md.md)]ISE en utilisant la communication à distance [!INCLUDE[wps_2](../Token/wps_2_md.md)]. Le paramètre - ShowCommandInfo remplace la fonction Get-SerializedCommand du module Microsoft.PowerShell.Utility, mais le script Get-SerializedCommand est toujours disponible pour prendre en charge les scripts de bas niveau.

-   Une nouvelle applet de commande, Get-ItemPropertyValue, permet d’obtenir la valeur d’une propriété sans utiliser de notation par points. Par exemple, dans les versions plus anciennes de [!INCLUDE[wps_2](../Token/wps_2_md.md)], vous pouvez exécuter la commande suivante pour obtenir la valeur de la propriété de base de l’application de la clé de Registre PowerShellEngine : **(Get-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\PowerShell\3\PowerShellEngine -Name ApplicationBase).ApplicationBase**. Désormais, dans [!INCLUDE[wps_2](../Token/wps_2_md.md)] 5.0, vous pouvez exécuter **Get-ItemPropertyValue -Path HKLM:\SOFTWARE\Microsoft\PowerShell\3\PowerShellEngine -Name ApplicationBase**.

-   La console [!INCLUDE[wps_2](../Token/wps_2_md.md)] utilise désormais une coloration de la syntaxe, tout comme dans [!INCLUDE[wps_2](../Token/wps_2_md.md)] ISE.

-   Un nouveau module, NetworkSwitch, contient des applets de commande permettant d’appliquer un commutateur, un réseau local virtuel (VLAN) et une configuration de port de commutateur réseau de couche 2 de base à des commutateurs réseau certifiés par logo [!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)].

-   Le paramètre FullyQualifiedName a été ajouté aux applets de commande Import-Module et Remove-Module, pour prendre en charge le stockage de plusieurs versions d’un même module.

-   Les applets de commande Save-Help, Update-Help, Import-PSSession, Export-PSSession et Get-Command disposent d’un nouveau paramètre, FullyQualifiedModule, de type ModuleSpecification.. Ajoutez ce paramètre pour spécifier un module par son nom complet.

-   La valeur de **$PSVersionTable.PSVersion** a été mise à jour. Il s’agit désormais de 5.0.

### <a name="BKMK_newDSC"></a>Nouvelles fonctionnalités dans la configuration d’état souhaité de Windows PowerShell

-   Le rehaussement du langage [!INCLUDE[wps_2](../Token/wps_2_md.md)] permet de définir des ressources de configuration d’état souhaité (DSC) [!INCLUDE[wps_2](../Token/wps_2_md.md)] à l’aide de classes. Importer-DscResource est désormais un vrai mot clé dynamique. [!INCLUDE[wps_2](../Token/wps_2_md.md)] analyse le module racine du module spécifié, en recherchant des classes contenant l’attribut DscResource . Vous pouvez désormais utiliser des classes pour définir des ressources DSC, dans lesquelles un fichier MOF ou un sous-dossier DSCResource dans le dossier du module ne sont pas requis. Un fichier de module [!INCLUDE[wps_2](../Token/wps_2_md.md)] peut contenir plusieurs classes de ressources DSC.

-   Un nouveau paramètre, ThrottleLimit, a été ajouté aux applets de commande suivantes dans le module PSDesiredStateConfiguration. Ajoutez le paramètre ThrottleLimit pour spécifier le nombre d’ordinateurs cibles ou d’appareils sur lesquels vous souhaitez que la commande opère simultanément.

    -   Get-DscConfiguration

    -   Get-DscConfigurationStatus

    -   Get-DscLocalConfigurationManager

    -   Restore-DscConfiguration

    -   Test-DscConfiguration

    -   Comparer-DscConfiguration

    -   Publish-DscConfiguration

    -   Set-DscLocalConfigurationManager

    -   Start-DscConfiguration

    -   Update-DscConfiguration

-   Avec le signalement d’erreurs DSC centralisé, outre que les informations d’erreur complètes sont enregistrées dans le journal des événements, celles-ci peuvent être envoyées à un emplacement central à des fins d’analyse ultérieure. Vous pouvez utiliser cet emplacement central pour stocker des erreurs de configuration DSC qui se sont produites pour un serveur quelconque dans son environnement. Une fois le serveur de rapports défini dans la métaconfiguration, toutes les erreurs sont envoyées au serveur de rapports et stockées dans une base de données. Vous pouvez configurer cette fonctionnalité, indépendamment du fait qu’un nœud cible soit configuré ou non pour extraire des configurations d’un serveur collecteur.

-   Les améliorations apportées à [!INCLUDE[wps_2](../Token/wps_2_md.md)] ISE facilitent la création de ressources DSC. Vous pouvez désormais effectuer les opérations suivantes.

    -   Énumération de toutes les ressources DSC dans un bloc **configuration** ou **node** en entrant **Ctrl+Espace** dans une ligne vide du bloc.

    -   Saisie semi-automatique sur les propriétés de ressources du type **enumeration**.

    -   Saisie semi-automatique sur la propriété **DependsOn** des ressources DSC, basée sur d’autres instances de ressources dans la configuration.

    -   Saisie semi-automatique via la touche Tab améliorée pour les valeurs de propriété de ressource.

-   Un utilisateur peut désormais exécuter une ressource sous un ensemble spécifié d’informations d’identification en ajoutant l’attribut **PSDscRunAsCredential** à un bloc de nœud. Par exemple, PSDscRunAsCredential = Get-Credential Contoso\DscUser. Cette fonctionnalité est utile pour créer des configurations qui exécutent le programme d’installation de Windows et des programmes d’installation exécutables, accèdent à la ruche du Registre par utilisateur, ou effectuent d’autres tâches en dehors du contexte de l’utilisateur actuel.

-   La prise en charge 32 bits (basée sur x86) a été ajoutée pour le mot clé **Configuration**.

-   [!INCLUDE[wps_2](../Token/wps_2_md.md)] inclut désormais la prise en charge de l’aide personnalisée pour les configurations DSC, définie par l’ajout de [CmdletBinding()] à la fonction de configuration générée.

-   Un nouvel attribut, **DscLocalConfigurationManager**, désigne un bloc de configuration en tant que métaconfiguration, qui sert à configurer le gestionnaire de configuration local DSC. Avec cet attribut, une configuration peut contenir uniquement des éléments qui configurent le gestionnaire de configuration local DSC. Pendant le traitement, cette configuration génère un fichier *.meta.mof qui est ensuite envoyé aux nœuds cibles appropriés en exécutant l’applet de commande Set-DscLocalConfigurationManager.

-   Les configurations partielles sont désormais autorisées dans [!INCLUDE[wps_2](../Token/wps_2_md.md)]5.0. Vous pouvez distribuer des documents de configuration à un nœud en plusieurs fragments. Pour qu’un nœud reçoive plusieurs fragments d’un document de configuration, il faut que son gestionnaire de configuration local soit configuré pour spécifier les fragments attendus.

-   La synchronisation entre ordinateurs est une nouveauté de DSC dans [!INCLUDE[wps_2](../Token/wps_2_md.md)]5.0. Avec les ressources WaitFor* intégrées (**WaitForAll**, **WaitForAny** et **WaitForSome**), vous pouvez désormais spécifier des dépendances entre ordinateurs lors d’exécutions de configuration, sans orchestration externe. Ces ressources fournissent une synchronisation de nœud à nœud à l’aide de connexions CIM sur le protocole WS-Man. Une configuration peut attendre que l’état d’une ressource spécifique d’un autre ordinateur change.

-   Une nouvelle fonctionnalité de sécurité de délégation, JEA (Just Enough Administration), tire parti de DSC et des instances d’exécution contraintes de [!INCLUDE[wps_2](../Token/wps_2_md.md)] pour protéger les entreprises contre la perte de données ou des actes préjudiciables commis par employés, intentionnellement ou non. Pour plus d’informations sur la fonctionnalité JEA, y compris l’emplacement à partir duquel vous pouvez télécharger la ressource DSC xJEA, voir [Just Enough Administration, Step by Step](http://blogs.technet.com/b/privatecloud/archive/2014/05/14/just-enough-administration-step-by-step.aspx) (en anglais).

-   Les nouvelles applets de commande suivantes ont été ajoutées au module PSDesiredStateConfiguration.

    -   Une nouvelle applet de commande, Get-DscConfigurationStatus, obtient des informations de haut niveau sur l’état de configuration à partir d’un nœud cible. Vous pouvez obtenir l’état de la dernière configuration ou de toutes les configurations.

    -   Une nouvelle applet de commande, Compare-DscConfiguration, compare une configuration spécifiée à l’état réel d’un ou plusieurs nœuds cibles.

    -   Une nouvelle applet de commande, Publish-DscConfiguration, copie un fichier MOF de configuration sur un nœud cible, mais n’applique pas la configuration. Cette configuration est appliquée durant le contrôle de cohérence suivant, ou quand vous exécutez l’applet de commande Update-DscConfiguration.

    -   Une nouvelle applet de commande, Test-DscConfiguration, permet de vérifier si une configuration obtenue correspond à la configuration souhaitée, en retournant la valeur True si c’est le cas, ou la valeur False si ça ne l’est pas.

    -   Une nouvelle applet de commande, Update-DscConfiguration, force le traitement d’une configuration. Si le gestionnaire de configuration local est en mode par extraction, l’applet de commande obtient la configuration à partir du serveur collecteur avant de l’appliquer.

### <a name="BKMK_newISE"></a>Nouvelles fonctionnalités dans Windows PowerShell ISE

-   Vous pouvez désormais modifier des scripts et fichiers [!INCLUDE[wps_2](../Token/wps_2_md.md)] distants dans une copie locale de [!INCLUDE[wps_2](../Token/wps_2_md.md)]ISE, en exécutant Enter-PSSession pour démarrer une session à distance sur l’ordinateur qui stocke les fichiers à modifier, puis en exécutant **PSEdit <path and file name on the remote computer>**. Cette fonctionnalité facilite la modification de fichiers [!INCLUDE[wps_2](../Token/wps_2_md.md)] stockés sur l’option d’installation minimale de Windows Server, où [!INCLUDE[wps_2](../Token/wps_2_md.md)]ISE ne peut pas s’exécuter.

-   L’applet de commande Start-Transcript est désormais prise en charge dans [!INCLUDE[wps_2](../Token/wps_2_md.md)]ISE.

-   Vous pouvez désormais déboguer des scripts à distance dans [!INCLUDE[wps_2](../Token/wps_2_md.md)]ISE.

-   Une nouvelle option de menu, **Interrompre tout** (Ctrl + B) arrête le débogueur pour les scripts s’exécutant tant en local et qu’à distance.

### <a name="BKMK_newOData"></a>Nouvelles fonctionnalités dans Windows PowerShell Web Services (Extension ISS Management OData)

-   Désormais, dans [!INCLUDE[wps_2](../Token/wps_2_md.md)] 5.0, vous pouvez générer un ensemble d’applets de commande [!INCLUDE[wps_2](../Token/wps_2_md.md)] basées sur la fonctionnalité exposée par un point de terminaison OData, en exécutant l’applet de commande Export-ODataEndpointProxy, figurant dans le nouveau module [Microsoft.PowerShell.OdataUtils](http://technet.microsoft.com/library/dn818507(v=wps.640).aspx).

### <a name="BKMK_5bugfix"></a>Correctifs de bogues importants dans Windows PowerShell 5.0

-   [!INCLUDE[wps_2](../Token/wps_2_md.md)] 5.0 inclut une nouvelle implémentation de COM, qui améliore sensiblement les performances lorsque vous travaillez avec des objets COM. Pour une démonstration vidéo de l’effet obtenu, voir [Com_Perf_Improvements](http://1drv.ms/1qu3UPZ).

-   Les performances de la première saisie semi-automatique via la touche Tab dans une session [!INCLUDE[wps_2](../Token/wps_2_md.md)] ont été sensiblement améliorées. Le temps d’exécution a en effet été raccourci de près de 500 ms.

## <a name="BKMK_wps4"></a>Nouvelles fonctionnalités dans Windows PowerShell 4.0
[!INCLUDE[psversion4](../Token/psversion4_md.md)] offre une compatibilité descendante. Les applets de commande, fournisseurs, modules, composants logiciels enfichables, scripts, fonctions et profils conçus pour [!INCLUDE[psversion3](../Token/psversion3_md.md)] et [!INCLUDE[psversion2](../Token/psversion2_md.md)] fonctionnent dans [!INCLUDE[psversion4](../Token/psversion4_md.md)] sans modification.

[!INCLUDE[psversion4](../Token/psversion4_md.md)] est installé par défaut sous [!INCLUDE[winblue_client_1](../Token/winblue_client_1_md.md)] et [!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)]. Pour installer [!INCLUDE[psversion4](../Token/psversion4_md.md)] sur Windows 7 avec SP1, ou Windows Server 2008 R2, téléchargez et installez [Windows Management Framework 4.0](http://www.microsoft.com/download/details.aspx?id=40855). Avant d'installer Windows Management Framework 4.0, veillez à prendre connaissance des détails du téléchargement et à vérifier la configuration système requise.

-   [Nouvelles fonctionnalités de Windows PowerShell](#BKMK_core)

-   [Nouvelles fonctionnalités de l'environnement d'écriture de scripts intégré (ISE) de Windows PowerShell](#BKMK_ise)

-   [Nouvelles fonctionnalités de Windows PowerShell Workflow](#BKMK_workflow)

-   [Nouvelles fonctionnalités de Windows PowerShell Web Services](#BKMK_psws)

-   [Nouvelles fonctionnalités de Windows PowerShell Web Access](#BKMK_powwa)

-   [Correctifs de bogues importants dans Windows PowerShell 4.0](#BKMK_bugs)

[!INCLUDE[psversion4](../Token/psversion4_md.md)] intègre les nouvelles fonctionnalités suivantes.

### <a name="BKMK_core"></a>Nouvelles fonctionnalités dans Windows PowerShell

-   **La configuration d’état souhaité [!INCLUDE[wps_2](../Token/wps_2_md.md)]** (DSC) est un nouveau système de gestion dans [!INCLUDE[psversion4](../Token/psversion4_md.md)], qui permet de déployer et de gérer les données de configuration de services logiciels et l’environnement dans lequel ces services s’exécutent. Pour plus d’informations sur DSC, voir [Prendre en main la configuration d’état souhaité Windows PowerShell](assetId:///c134aa32-b085-4656-9a89-955d8ff768d0).

-   L’applet de commande **Save-Help** permet désormais d’enregistrer l’aide pour des modules installés sur des ordinateurs distants. Vous pouvez utiliser l’applet de commande Save-Help pour télécharger le module d’aide à partir d’un client connecté à Internet (sur lequel les modules sur lesquels vous avez besoin d’aide ne sont pas forcément tous installés), puis copier l’aide enregistrée dans un dossier partagé distant ou sur un ordinateur distant n’ayant pas accès à Internet.

-   Le débogueur [!INCLUDE[wps_2](../Token/wps_2_md.md)] a été amélioré pour permettre de déboguer des flux de travail de [!INCLUDE[wps_2](../Token/wps_2_md.md)], ainsi que des scripts qui s’exécutent sur des ordinateurs distants. Il est désormais possible de déboguer les flux de travail de [!INCLUDE[wps_2](../Token/wps_2_md.md)] au niveau du script soit à partir de la ligne de commande de [!INCLUDE[wps_2](../Token/wps_2_md.md)], soit à partir de [!INCLUDE[ise_2](../Token/ise_2_md.md)]. Les scripts de [!INCLUDE[wps_2](../Token/wps_2_md.md)], y compris les flux de travail de scripts, peuvent désormais être débogués sur des sessions à distance. Les sessions de débogage à distance sont conservées sur des sessions à distance de [!INCLUDE[wps_2](../Token/wps_2_md.md)] qui sont déconnectées, puis reconnectées.

-   Le paramètre **RunNow** pour les applets de commande **Register-ScheduledJob** et **Set-ScheduledJob** vous évite de devoir définir une date et une heure de démarrage immédiat pour les travaux à l’aide du paramètre **Trigger**.

-   Les applets de commande **Invoke-RestMethod** et **Invoke-WebRequest** vous permettent désormais de définir tous les en-têtes à l’aide du paramètre Headers. Bien que ce paramètre ait toujours existé, il faisait partie des quelques paramètres d'applets de commande web qui généraient des erreurs ou des exceptions.

-   L’applet de commande **Get-Module** dispose d’un nouveau paramètre, **FullyQualifiedName**, du type **ModuleSpecification[]**. Le paramètre **FullyQualifiedName** de l’applet de commande Get-Module permet désormais de spécifier un module par son nom, sa version et éventuellement son GUID.

-   Le paramètre de stratégie d’exécution par défaut sur [!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)]winblue_server_2** est **RemoteSigned. Le paramètre par défaut de [!INCLUDE[winblue_client_2](../Token/winblue_client_2_md.md)] n’a pas été modifié.

-   Désormais, dans [!INCLUDE[psversion4](../Token/psversion4_md.md)], l’appel de méthode à l’aide de noms de méthodes dynamiques est pris en charge. Vous pouvez utiliser une variable pour stocker un nom de méthode, puis appeler la méthode de façon dynamique en appelant la variable.

-   Les travaux de flux de travail asynchrones ne sont plus supprimés au terme du délai d’attente spécifié par le paramètre commun de flux de travail **PSElapsedTimeoutSec**.

-   Un nouveau paramètre, **RepeatIndefinitely**, a été ajouté aux applets de commande **New-JobTrigger** et **Set-JobTrigger**. Celui-ci vous évite de devoir affecter une valeur **TimeSpan.MaxValue** au paramètre **RepetitionDuration** pour exécuter un travail planifié à plusieurs reprises pendant une durée indéterminée.

-   Le paramètre **Passthru** a été ajouté aux applets de commande **Enable-JobTrigger** et **Disable-JobTrigger**. Le paramètre Passthru affiche tous les objets créés ou modifiés par votre commande.

-   Les noms des paramètres utilisés pour spécifier un groupe de travail dans les applets de commande **Add-Computer** et **Remove-Computer** sont désormais cohérents. Les deux applets de commande utilisent désormais le paramètre **WorkgroupName**.

-   Un nouveau paramètre commun, **PipelineVariable**, a été ajouté. PipelineVariable vous permet d'enregistrer les résultats d'une commande dirigée (ou une partie de celle-ci) en tant que variable pouvant être passée via le reste du pipeline.

-   Le filtrage de collection à l'aide d'une syntaxe de méthode est désormais pris en charge. Cela signifie que vous pouvez désormais filtrer une collection d’objets à l’aide d’une syntaxe simplifiée, semblable à celle utilisée pour Where() ou Where-Object, dont le format est celui d’un appel de méthode. Voici un exemple : (Get-Process).where({$_.Name -match ’powershell’})

-   L’applet de commande **Get-Process** dispose d’un nouveau paramètre booléen, **IncludeUserName**.

-   Une nouvelle applet de commande, **Get-FileHash**, a été ajoutée. Celle-ci retourne un hachage de fichier dans l’un des formats disponibles pour un fichier spécifié.

-   Dans [!INCLUDE[psversion4](../Token/psversion4_md.md)], si un module utilise la clé **DefaultCommandPrefix** dans son manifeste ou si l’utilisateur importe un module avec le paramètre **Prefix**, la propriété **ExportedCommands** du module affiche les commandes de celui-ci avec le préfixe. Quand vous exécutez les commandes à l’aide de la syntaxe propre au module (NomDeModule\NomDeCommande), les noms des commandes doivent inclure le préfixe.

-   La valeur de **$PSVersionTable.PSVersion** a été mise à jour. Il s’agit désormais de 4.0.

-   Le comportement de l’opérateur **Where()** a changé. `Collection.Where('property –match name')` n’accepte plus d’expression de chaîne au format `"Property –CompareOperator Value"`. En revanche, l’opérateur **Where()** accepte toujours les expressions de chaîne au format bloc de script.

### <a name="BKMK_ise"></a>Nouvelles fonctionnalités dans l’environnement d’écriture de scripts intégré (ISE) de Windows PowerShell

-   [!INCLUDE[ise_2](../Token/ise_2_md.md)] prend en charge le débogage et le débogage de script à distance de [!INCLUDE[ps_workflow_2](../Token/ps_workflow_2_md.md)].

-   La prise en charge d’IntelliSense a été ajoutée pour les configurations et les fournisseurs de configuration d’état souhaité [!INCLUDE[wps_2](../Token/wps_2_md.md)].

### <a name="BKMK_workflow"></a>Nouvelles fonctionnalités dans le flux de travail de Windows PowerShell

-   Un nouveau paramètre commun, **PipelineVariable**, est désormais pris en charge dans le contexte des pipelines itératifs, comme ceux utilisés par System Center Orchestrator. Il s’agit en fait des pipelines qui exécutent simplement les commandes de gauche à droite, par opposition à une exécution parsemée via une diffusion en continu.

-   La liaison de paramètre a été considérablement améliorée pour fonctionner en dehors des scénarios de saisie semi-automatique par tabulation, comme avec les commandes qui n'existent pas dans l'instance d'exécution actuelle.

-   Les activités de conteneur personnalisées sont désormais prises en charge dans [!INCLUDE[ps_workflow_2](../Token/ps_workflow_2_md.md)]. Si un paramètre d’activité est de type **Activity** ou **Activity[]** ou bien une collection générique d’activités, et que l’utilisateur a fourni un bloc de script en tant qu’argument, [!INCLUDE[ps_workflow_2](../Token/ps_workflow_2_md.md)] convertit le bloc de script au format XAML, comme lors d’une compilation normale de script à flux de travail [!INCLUDE[wps_2](../Token/wps_2_md.md)].

-   Après un incident, le flux de travail de [!INCLUDE[wps_2](../Token/wps_2_md.md)] se reconnecte automatiquement aux nœuds gérés.

-   Vous pouvez également limiter les instructions d’activités **Foreach -Parallel** à l’aide de la propriété **ThrottleLimit**.

-   Le paramètre commun **ErrorAction** offre une nouvelle valeur valide, **Suspend**, réservée exclusivement aux flux de travail.

-   Un point de terminaison de flux de travail se ferme désormais automatiquement en l’absence de sessions actives, de tâches en cours ou de tâches en attente. Cette fonctionnalité conserve les ressources sur l'ordinateur jouant le rôle de serveur de flux de travail quand les conditions de fermeture automatique sont remplies.

### <a name="BKMK_psws"></a>Nouvelles fonctionnalités dans Windows PowerShell Web Services

-   Si une erreur se produit dans [!INCLUDE[wps_2](../Token/wps_2_md.md)] Web Services (PSWS ou extension ISS Management OData) alors qu’une applet de commande est en cours d’exécution, des messages d’erreur plus détaillés sont retournés à l’appelant. En outre, les codes d’erreur suivent [instructions relatives aux codes d’erreur d’API REST de Windows Azure](http://msdn.microsoft.com/library/windowsazure/dd179357.aspx).

-   Un point de terminaison peut désormais définir la version de l'API et forcer l'utilisation d'une version spécifique de l'API. En cas d'incompatibilité de version entre le client et le serveur, les erreurs sont affichées à la fois sur le client et le serveur.

-   La génération automatique des valeurs des champs manquants dans le schéma de répartition simplifie la gestion du schéma. La génération se produit, comme point de départ utile, même si le schéma de distribution n'existe pas.

-   La gestion des types dans PSWS a été améliorée pour prendre en charge les types qui utilisent un constructeur autre que le constructeur par défaut. Le comportement adopté est similaire à celui de **PSTypeConverter** dans [!INCLUDE[wps_2](../Token/wps_2_md.md)]. Vous pouvez ainsi utiliser des types complexes avec PSWS.

-   PSWS permet désormais d'étendre une instance associée lors de l'exécution d'une requête. Pour le contenu binaire plus volumineux (comme des images, des fichiers audio ou des vidéos), le coût de transfert est élevé. Il est donc préférable de transférer les données binaires sans encodage. PSWS utilise des flux de ressources nommés pour le transfert sans encodage. Le flux de ressources nommé est une propriété d’une entité de type **Edm.Stream**. Chaque flux de ressources nommé possède un URI distinct pour les opérations GET ou UPDATE.

-   Les actions OData proposent désormais un mécanisme pour appeler des méthodes non CRUD (Create, Read, Update et Delete) sur une ressource. Vous pouvez appeler une action en envoyant une demande HTTP POST à l'URI qui est défini pour l'action. Les paramètres de l'action sont définis dans le corps de la demande POST.

-   Par souci de cohérence avec les recommandations Windows Azure, toutes les URL doivent être simplifiées. Suite à une modification apportée à **Key As Segment**, des clés uniques peuvent être représentées en tant que segments. Comme précédemment, si des références utilisent plusieurs valeurs de clé, les valeurs doivent être séparées par des virgules et entourées de parenthèses.

-   Avant cette version de PSWS, la seule façon d’effectuer des opérations Create, Update ou Delete consistait à appeler Post, Put ou Delete sur une ressource de niveau supérieur. Dans cette version de PSWS, les opérations sur les ressources contenues permettent non seulement d'obtenir les mêmes résultats, mais aussi d'atteindre les mêmes ressources de manière moins directe (comme si ces ressources étaient contenues).

### <a name="BKMK_powwa"></a>Nouvelles fonctionnalités dans Accès Windows PowerShell Web

-   Vous pouvez vous déconnecter de sessions existantes et vous y reconnecter via la console web de [!INCLUDE[pswa_2](../Token/pswa_2_md.md)]. Le bouton **Enregistrer** dans la console web permet de vous déconnecter d’une session sans la supprimer et de vous y reconnecter ultérieurement.

-   Vous pouvez afficher les paramètres par défaut dans la page de connexion. Pour afficher les paramètres par défaut, configurez les valeurs de tous les paramètres affichés dans la zone **Paramètres de connexion facultatifs** de la page de connexion dans un fichier nommé **web.config**. Vous pouvez utiliser le fichier **web.config** pour configurer tous les paramètres de connexion facultatifs, à l’exception d’un deuxième ou d’un autre ensemble d’informations d’identification.

-   Dans [!INCLUDE[winblue_server_2](../Token/winblue_server_2_md.md)], vous pouvez gérer à distance les règles d’autorisation pour [!INCLUDE[pswa_2](../Token/pswa_2_md.md)]. Les applets de commande **Add-PswaAuthorizationRule** et **Test-PswaAuthorizationRule** incluent désormais un paramètre Credential qui permet aux administrateurs de gérer les règles d’autorisation à partir d’un ordinateur distant ou dans une session [!INCLUDE[pswa_2](../Token/pswa_2_md.md)].

-   Vous pouvez désormais avoir plusieurs sessions [!INCLUDE[pswa_2](../Token/pswa_2_md.md)] dans une même session de navigateur. Pour cela, il vous suffit d’ouvrir un nouvel onglet de navigateur pour chaque session. Il n’est plus nécessaire d’ouvrir une nouvelle session de navigateur pour se connecter à une nouvelle session dans la console web de [!INCLUDE[wps_2](../Token/wps_2_md.md)].

### <a name="BKMK_bugs"></a>Correctifs de bogues notables dans Windows PowerShell 4.0

-   L’applet de commande **Get-Counter** peut désormais retourner des compteurs qui contiennent une apostrophe dans les éditions françaises de Windows.

-   Vous pouvez désormais afficher la méthode **GetType** sur des objets désérialisés.

-   Les instructions **#Requires** permettent désormais aux utilisateurs d’exiger des droits d’accès réservés aux administrateurs, si nécessaire.

-   L’applet de commande **Import-Csv** ignore désormais les lignes vides.

-   Un problème lié à une utilisation trop importante de la mémoire par [!INCLUDE[ise_2](../Token/ise_2_md.md)] lors de l’exécution d’une commande **Invoke-WebRequest** a été résolu.

-   L’applet de commande **Get-Module** affiche désormais les versions des modules dans une colonne **Version**.

-   L’applet de commende Remove-Item -Recurse supprime désormais les éléments des sous-dossiers comme prévu.

-   La propriété **UserName** a été ajoutée aux objets de sortie **Get-Process**.

-   L’applet de commande **Invoke-RestMethod** retourne désormais tous les résultats disponibles.

-   L’applet de commende **Add\-Member** s’applique désormais aux tables de hachage, même si celles-ci n’ont pas encore été sollicitées.

-   L’applet de commande **Select-Object –Expand** n’échoue plus et ne génère plus d’exception si la valeur de la propriété est null ou vide.

-   L’applet de commende **Get-Process** peut désormais être utilisée dans un pipeline avec d’autres commandes qui obtiennent la propriété **ComputerName** d’objets.

-   Les applets de commande **ConvertTo-Json** et **ConvertFrom-Json** peuvent désormais accepter les termes entre guillemets doubles, et leurs messages d’erreur sont localisables.

-   L’applet de commande **Get-Job** retourne désormais toutes les travaux planifiés terminés, même dans de nouvelles sessions.

-   Les problèmes liés au montage et au démontage de disques durs virtuels à l’aide du fournisseur **FileSystem** dans [!INCLUDE[psversion4](../Token/psversion4_md.md)] ont été résolus. [!INCLUDE[wps_2](../Token/wps_2_md.md)] peut désormais détecter de nouveaux lecteurs quand ils sont montés dans la même session.

-   Il n’est plus nécessaire de charger explicitement les modules **ScheduledJob** et **Workflow** pour utiliser leurs types de travaux.

-   Les performances du processus d'importation de flux de travail définissant des flux de travail imbriqués ont été améliorées. Ce processus est désormais plus rapide.

## <a name="BKMK_wps3"></a>Nouvelles fonctionnalités dans Windows PowerShell 3.0
[!INCLUDE[psversion3](../Token/psversion3_md.md)] intègre les nouvelles fonctionnalités suivantes.

-   [Windows PowerShell Workflow](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_Workflow)

-   [Windows PowerShell Web Access](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_WebAccess)

-   [Nouvelles fonctionnalités de Windows PowerShell ISE](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_ISE)

-   [Prise en charge de Microsoft .NET Framework 4.0](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_NET4)

-   [Prise en charge de l'environnement de préinstallation Windows](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_WinPE)

-   [Sessions déconnectées](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_Disconnected)

-   [Connectivité fiable des sessions](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_Robust)

-   [Système d'aide actualisable](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_UpHelp)

-   [Aide en ligne améliorée](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_Online)

-   [Intégration de CIM](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_CIM)

-   [Fichiers de configuration de session](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_ConfigFile)

-   [Travaux planifiés et intégration du Planificateur de tâches](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_ScheduledJob)

-   [Améliorations apportées au langage Windows PowerShell](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_Lang)

-   [Nouvelles applets de commande Core](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_Core)

-   [Améliorations apportées aux applets de commande et aux fournisseurs Core existants](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_Prov)

-   [Importation et découverte des modules à distance](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_REM)

-   [Saisie semi-automatique par tabulation améliorée](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_TAB)

-   [Chargement automatique des modules](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_AutoLoad)

-   [Améliorations apportées aux fonctionnalités des modules](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_MOD)

-   [Découverte des commandes simplifiée](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_SIMPLE)

-   [Prise en charge améliorée de la journalisation, du diagnostic et de la stratégie de groupe](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_LOG)

-   [Améliorations apportées à la mise en forme et à la sortie](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_OUT)

-   [Améliorations apportées aux fonctionnalités de l'hôte de console](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_HOST)

-   [Nouvelles API Cmdlet et Hosting](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_API)

-   [Améliorations des performances](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_PERF)

-   [Prise en charge de RunAs et de SharedHost](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_RUNAS)

-   [Améliorations apportées à la gestion des caractères spéciaux](../Topic/What-s-New-in-Windows-PowerShell.md#BKMK_CHAR)

### <a name="BKMK_Workflow"></a>Flux de travail Windows PowerShell
Grâce à [!INCLUDE[ps_workflow_1](../Token/ps_workflow_1_md.md)], vous bénéficiez de toute la puissance de Windows Workflow Foundation dans [!INCLUDE[mshshort](../Token/mshshort_md.md)]. Vous pouvez écrire des flux de travail en XAML ou dans le langage [!INCLUDE[mshshort](../Token/mshshort_md.md)], et les exécuter de la même façon qu’une applet de commande. L’applet de commande [Get-Command](assetId:///59c6d302-6e8c-48b7-a6f6-f0172df936ad) obtient les commandes de flux de travail et l’applet de commande [Get-Help](assetId:///1f46eeb4-49d7-4bec-bb29-395d9b42f54a) obtient de l’aide sur les flux de travail.

Les flux de travail sont des séquences d’activités de gestion de plusieurs ordinateurs. Ces séquences sont longues, reproductibles, fréquentes, parallèles et redémarrables. Elles peuvent aussi être interrompues et suspendues. Il est possible de reprendre des flux de travail suite à une interruption accidentelle ou intentionnelle, une indisponibilité du réseau, un redémarrage de Windows ou une panne de courant.

Les flux de travail sont aussi portables, c'est-à-dire qu'ils peuvent être exportés vers des fichiers XAML ou importés à partir de ceux-ci. Vous pouvez écrire des configurations de session personnalisées qui permettent à des utilisateurs délégués ou subordonnés d'exécuter un flux de travail ou les activités qu'il contient.

Les avantages de [!INCLUDE[ps_workflow_2](../Token/ps_workflow_2_md.md)] sont les suivants :

-   **Automatisation des tâches séquencées et longues.**

-   **Surveillance à distance des tâches longues**. Visibilité à tout moment de l'état et de la progression des activités.

-   **Gestion de plusieurs ordinateurs.** Exécution simultanée de tâches en tant que flux de travail sur des centaines de nœuds gérés. [!INCLUDE[ps_workflow_2](../Token/ps_workflow_2_md.md)] inclut une bibliothèque intégrée de paramètres de gestion communs, tels que **PSComputerName**, qui prennent en charge les scénarios de gestion de plusieurs ordinateurs.

-   **Exécution en une seule tâche de processus complexes.** Vous pouvez combiner des scripts associés dans un seul flux de travail pour implémenter un scénario complet de bout en bout.

-   **Persistance.** Un flux de travail est enregistré à des points de contrôle spécifiques définis par son auteur, ce qui permet de reprendre le flux de travail à partir de la dernière tâche persistante (ou point de contrôle) au lieu de redémarrer le flux de travail depuis le début.

-   **Fiabilité.** Récupération après défaillance automatisée. Les flux de travail survivent aux redémarrages planifiés et non planifiés. Vous pouvez suspendre l'exécution d'un flux de travail, puis le reprendre à partir du dernier point de persistance. Les auteurs de flux de travail peuvent désigner des activités spécifiques à réexécuter en cas de défaillance sur un ou plusieurs nœuds gérés.

-   **Possibilité de déconnexion, de reconnexion et d'exécution dans des sessions déconnectées.** Les utilisateurs peuvent se connecter au serveur de flux de travail et s'en déconnecter, mais le flux de travail s'exécute en continu. Vous pouvez fermer la session sur l'ordinateur client, ou redémarrer ce dernier, et surveiller l'exécution du flux de travail à partir d'un autre ordinateur sans interrompre le flux de travail.

-   **Planification.** Les tâches de flux de travail peuvent être planifiées comme une applet de commande ou un script [!INCLUDE[mshshort](../Token/mshshort_md.md)].

-   **Limitation des flux de travail et des connexions.** Vous pouvez limiter l’exécution des flux de travail et les connexions aux nœuds, ce qui permet de prendre en charge des scénarios évolutifs et à haute disponibilité.

### <a name="BKMK_WebAccess"></a>Accès Web Windows PowerShell
[!INCLUDE[pswa_1](../Token/pswa_1_md.md)] est une fonctionnalité de [!INCLUDE[win8_server_2](../Token/win8_server_2_md.md)] qui permet aux utilisateurs d’exécuter des commandes et des scripts Windows PowerShell dans une console web. Les appareils qui utilisent la console web ne nécessitent ni [!INCLUDE[mshshort](../Token/mshshort_md.md)], ni un logiciel de gestion à distance, ni l’installation d’un plug-in de navigateur. Il suffit de disposer d’une passerelle [!INCLUDE[pswa_2](../Token/pswa_2_md.md)] correctement configurée, et d’un navigateur d’appareil client prenant en charge JavaScript® et acceptant les cookies.

Pour plus d’informations, voir [Déployer un Accès Windows PowerShell Web](http://go.microsoft.com/fwlink/p/?LinkID=221050).

### <a name="BKMK_ISE"></a>Nouvelles fonctionnalités dans Windows PowerShell ISE
Pour [!INCLUDE[psversion3](../Token/psversion3_md.md)], [!INCLUDE[ise_1](../Token/ise_1_md.md)] comprend de nombreuses nouveautés, notamment IntelliSense, une fenêtre Show-Command, un volet de console unifiée, des extraits de code, la correspondance d’accolade, des sections à développement/réduction, l’enregistrement automatique, une liste des éléments récents, la copie riche, la copie de blocs, ainsi que la prise en charge complète de l’écriture de flux de travail à l’aide de scripts Windows PowerShell. Pour plus d’informations, voir [about_Windows_PowerShell_ISE [v3]](assetId:///dfa54d47-60c6-4fff-8197-c747e8d411bb).

### <a name="BKMK_NET4"></a>Prise en charge de Microsoft .NET Framework 4
Windows PowerShell repose sur le Common Language Runtime 4.0. Les auteurs d’applets de commande, de scripts et de flux de travail peuvent utiliser les nouvelles classes Microsoft .NET Framework 4 de Windows PowerShell. Ils peuvent ainsi bénéficier de fonctionnalités comme la compatibilité et le déploiement d’applications, Managed Extensibility Framework, l’informatique parallèle, la mise en réseau, Windows Communication Foundation et Windows Workflow Foundation.

### <a name="BKMK_WinPE"></a>Prise en charge de l’environnement de préinstallation Windows
Windows PowerShell 3.0 est un composant facultatif de l'environnement de préinstallation Windows (WinPE) 4.0 pour Windows 8. Windows PE est un système d’exploitation minimal qui permet de démarrer un ordinateur sans système d’exploitation, et qui le prépare en vue de l’installation de Windows. Windows PE permet de partitionner et formater des disques durs, de copier des images de disque sur un ordinateur et d’initier l’installation de Windows à partir d’un partage réseau. Windows PowerShell 3.0 peut être utilisé sur Windows PE pour gérer des scénarios de déploiement, de diagnostic et de récupération.

### <a name="BKMK_Disconnected"></a>Sessions déconnectées
Depuis Windows PowerShell 3.0, les sessions persistantes gérées par l’utilisateur (« PSSessions ») que vous créez à l’aide de l’applet de commande New-PSSession sont enregistrées sur l’ordinateur distant. Elles ne dépendent donc plus de la session dans laquelle elles ont été créées.

Vous pouvez désormais vous déconnecter d'une session sans interrompre les commandes en cours d'exécution dans la session. Vous pouvez fermer la session et arrêter votre ordinateur. Par la suite, vous pouvez vous reconnecter à la session à partir d'une session différente sur le même ordinateur ou un ordinateur différent.

Le paramètre **ComputerName** de l’applet de commande [Get-PSSession](assetId:///b2b10531-d0df-4746-b877-e75c09955cb6) obtient désormais toutes les sessions de l’utilisateur qui se connectent à l’ordinateur, même si elles ont été démarrées dans une session différente sur un autre ordinateur. Vous pouvez vous connecter aux sessions, obtenir les résultats des commandes, démarrer de nouvelles commandes, puis vous déconnecter de la session.

De nouvelles applets de commande ont été ajoutées pour prendre en charge la fonctionnalité Sessions déconnectées, notamment [Disconnect-PSSession](assetId:///f8f95111-612f-4cba-9098-77904b0473d8), [Connect-PSSession](assetId:///b803dd29-f208-4079-80d4-db04d778f060) et Receive-PSSession. Par ailleurs, de nouveaux paramètres ont été ajoutés aux applets de commande qui gèrent PSSessions, comme le paramètre **InDisconnectedSession** de l’applet de commande [Invoke-Command](assetId:///906b4b41-7da8-4330-9363-e7164e5e6970).

La fonctionnalité Sessions déconnectées n'est prise en charge que si les ordinateurs situés à chaque extrémité de la connexion (le « client » à l'origine et le « serveur » à la fin) exécutent Windows PowerShell 3.0.

### <a name="BKMK_Robust"></a>Connectivité fiable des sessions
Windows PowerShell 3.0 détecte les pertes inattendues de connectivité entre le client et le serveur. En cas de perte de connectivité, il tente de la rétablir et de reprendre l'exécution automatiquement. Si la connexion client-serveur ne peut pas être rétablie dans le délai imparti, l’utilisateur en est informé et la session est déconnectée. Lors de la tentative de reconnexion, Windows PowerShell fournit des commentaires en continu à l'utilisateur.

Si la session déconnectée a été démarrée à l'aide de l'applet de commande InvokeCommand, Windows PowerShell crée une tâche pour la session déconnectée pour faciliter la reconnexion et la reprise de l'exécution.

Ces fonctionnalités rendent l’expérience de communication à distance plus fiable et facilitent la récupération. Elles permettent aussi aux utilisateurs d’effectuer des tâches longues qui nécessitent des sessions fiables, comme des flux de travail.

### <a name="BKMK_UpHelp"></a>Système d’aide actualisable
Vous pouvez à présent télécharger des fichiers d'aide mis à jour pour les applets de commande dans vos modules. L’applet de commande [Update-Help](assetId:///93e1d870-ace6-432b-8778-8920291d7545) identifie les fichiers d’aide les plus récents, les télécharge à partir d’Internet, les décompresse, les valide, puis les installe dans le répertoire spécifique à la langue du module.

Pour utiliser les fichiers d’aide mis à jour, tapez simplement `Get-Help`. Il n’est pas nécessaire de redémarrer Windows ou [!INCLUDE[mshshort](../Token/mshshort_md.md)]. Pour mettre à jour l’aide des modules dans le répertoire $pshome, démarrez [!INCLUDE[mshshort](../Token/mshshort_md.md)] avec l’option « Exécuter en tant qu’administrateur ».

Pour prendre en charge les utilisateurs qui n’ont pas accès à Internet et ceux qui se trouvent derrière des pare-feu, la nouvelle applet de commande [Save-Help](assetId:///aed94f90-b73f-4e25-a25d-7c18d9f161fa) télécharge les fichiers d’aide vers un répertoire du système de fichiers, tel qu’un partage de fichiers. Les utilisateurs peuvent ensuite utiliser l’applet de commande [Update-Help](assetId:///93e1d870-ace6-432b-8778-8920291d7545) pour obtenir les fichiers d’aide à jour à partir du partage de fichiers.

Vous pouvez utiliser l’applet de commande [Update-Help](assetId:///93e1d870-ace6-432b-8778-8920291d7545) pour mettre à jour les fichiers d’aide de tous les modules ou de certains d’entre eux dans toutes les cultures d’interface utilisateur prises en charge. Vous pouvez même placer une commande [Update-Help](assetId:///93e1d870-ace6-432b-8778-8920291d7545) dans votre profil [!INCLUDE[mshshort](../Token/mshshort_md.md)]. Par défaut, [!INCLUDE[mshshort](../Token/mshshort_md.md)] télécharge les fichiers d’aide d’un module au maximum une fois par jour.

Les modules [!INCLUDE[win8_client_2](../Token/win8_client_2_md.md)] et [!INCLUDE[win8_server_2](../Token/win8_server_2_md.md)] n’incluent pas de fichiers d’aide. Pour télécharger les derniers fichiers d’aide, tapez `Update-Help`. Pour plus d’informations, tapez `Get-Help` (sans paramètre) ou consultez [about_Updatable_Help](assetId:///10bba75c-f4ac-4ca1-bbf3-8f34dd521ffe).

Si les fichiers d’aide d’une applet de commande ne sont pas installés sur l’ordinateur, l’applet de commande [Get-Help](assetId:///1f46eeb4-49d7-4bec-bb29-395d9b42f54a) affiche désormais une aide générée automatiquement. L’aide générée automatiquement contient la syntaxe de la commande et des instructions relatives à l’utilisation de l’applet de commande [Update-Help](assetId:///93e1d870-ace6-432b-8778-8920291d7545) pour télécharger les fichiers d’aide.

Tout auteur de module peut prendre en charge l'aide actualisable. Vous pouvez soit inclure des fichiers d'aide dans le module et utiliser l'aide actualisable pour les mettre à jour, soit omettre les fichiers d'aide et utiliser l'aide actualisable pour les installer. Pour plus d’informations sur la prise en charge de l’aide actualisable, voir [Prise en charge de l’aide actualisable](http://go.microsoft.com/FWLink/?LinkID=242129) dans MSDN.

### <a name="BKMK_Online"></a>Aide en ligne améliorée
L’aide en ligne de [!INCLUDE[mshshort](../Token/mshshort_md.md)] est une ressource précieuse pour tous les utilisateurs, mais elle est particulièrement importante pour les utilisateurs qui ne peuvent pas ou ne veulent pas installer des fichiers d’aide actualisés.

Pour accéder à l’aide en ligne relative à une applet de commande [!INCLUDE[mshshort](../Token/mshshort_md.md)], tapez :

```
Get-Help <cmdlet-name> -Online
```

[!INCLUDE[mshshort](../Token/mshshort_md.md)] ouvre la version en ligne de la rubrique d’aide dans votre navigateur Internet par défaut.

La fonctionnalité **Get-Help -Online** dans [!INCLUDE[psversion3](../Token/psversion3_md.md)] est encore plus performante, car elle fonctionne même si les fichiers d’aide correspondant à l’applet de commande ne sont pas installés sur l’ordinateur. La fonctionnalité **Get-Help -Online** obtient l’URI de la rubrique d’aide en ligne à partir de la propriété HelpUri d’applets de commande et de fonctions avancées.

```
PS C:\>(Get-Command Get-ScheduledJob).HelpUri
http://go.microsoft.com/fwlink/?LinkID=223923
```

Depuis [!INCLUDE[psversion3](../Token/psversion3_md.md)], les auteurs d’applets de commande en C# peuvent renseigner la propriété **HelpUri** en créant un attribut **HelpUri** sur la classe de l’applet de commande. Les auteurs de fonctions avancées peuvent définir une propriété **HelpUri** sur l’attribut **CmdletBinding**. La valeur de la propriété **HelpUri** doit commencer par « http » ou « https ».

Il est aussi possible d’inclure une valeur **HelpUri** dans le premier lien associé d’un fichier d’aide d’applet de commande en XML ou la directive .Link de l’aide basée sur les commentaires dans une fonction.

Pour plus d’informations sur la prise en charge de l’aide en ligne, voir [Supporting Online Help](http://go.microsoft.com/fwlink/?LinkId=242132) (en anglais) dans MSDN.

### <a name="BKMK_CIM"></a>Intégration de CIM
[!INCLUDE[psversion3](../Token/psversion3_md.md)] prend en charge le modèle CIM (Common Information Model). Celui-ci fournit des définitions communes pour les informations de gestion des systèmes, réseaux, applications et services, ce qui permet l’échange d’informations de gestion entre systèmes hétérogènes. La prise en charge du modèle CIM dans [!INCLUDE[psversion3](../Token/psversion3_md.md)] permet la création d’applets de commande Windows PowerShell basées sur des classes CIM nouvelles ou existantes, la création de commandes basées sur des fichiers XML de définition d’applets de commande, ainsi que la prise en charge de l’API .NET Framework CIM, des applets de commande de gestion CIM et des fournisseurs WMI 2.0.

### <a name="BKMK_ConfigFile"></a>Fichiers de configuration de session
Depuis [!INCLUDE[psversion3](../Token/psversion3_md.md)], vous pouvez concevoir une configuration de session personnalisée à l’aide d’un fichier. Le nouveau fichier de configuration de session vous permet de déterminer l'environnement des sessions qui utilisent la configuration de session, y compris : les modules, scripts et fichiers de format chargés dans les sessions ; les applets de commande et éléments de langage que les utilisateurs peuvent utiliser ; les modules et scripts qu'ils peuvent s'exécuter ; ainsi que les variables qu'ils peuvent afficher.

Vous pouvez concevoir soit une session dans laquelle les utilisateurs peuvent uniquement exécuter les applets de commande d'un module particulier, soit une session dans laquelle les utilisateurs disposent à la fois d'un accès complet à tous les modules avec tous les éléments de langage et d'un accès aux scripts qui effectuent des tâches avancées.

Dans les versions précédentes de [!INCLUDE[mshshort](../Token/mshshort_md.md)], le contrôle à ce niveau était uniquement disponible aux personnes capables d’écrire un programme en C# ou un script de démarrage complexe. À présent, tout membre du groupe Administrateurs sur l'ordinateur peut personnaliser une configuration de session à l'aide d'un fichier de configuration.

Pour créer un fichier de configuration de session, utilisez l’applet de commande [New-PSSessionConfigurationFile](assetId:///5f3e3633-6e90-479c-aea9-ba45a1954866). Pour appliquer le fichier de configuration de session à une configuration de session, utilisez l’applet de commande [Register-PSSessionConfiguration](assetId:///e9152ae2-bd6d-4056-9bc7-dc1893aa29ea) ou [Set-PSSessionConfiguration](assetId:///b21fbad3-1759-4260-b206-dcb8431cd6ea).

Pour plus d’informations, voir [about_Session_Configuration_Files](assetId:///c7217447-1ebf-477b-a8ef-4dbe9a1473b8) et [New-PSSessionConfigurationFile](assetId:///5f3e3633-6e90-479c-aea9-ba45a1954866).

### <a name="BKMK_ScheduledJob"></a>Travaux planifiés et intégration du Planificateur de tâches
Vous pouvez désormais planifier des travaux de [!INCLUDE[mshshort](../Token/mshshort_md.md)] en arrière-plan, puis les gérer dans [!INCLUDE[mshshort](../Token/mshshort_md.md)] et dans le Planificateur de tâches.

Les travaux planifiés de [!INCLUDE[mshshort](../Token/mshshort_md.md)] sont des tâches hybrides qui regroupent les avantages des travaux de [!INCLUDE[mshshort](../Token/mshshort_md.md)] en arrière-plan et des tâches du Planificateur de tâches.

Au même titre que les travaux de [!INCLUDE[mshshort](../Token/mshshort_md.md)] en arrière-plan, les travaux planifiés s’exécutent de manière asynchrone en arrière-plan. Vous pouvez gérer les instances de travaux planifiés terminés à l’aide d’applets de commande job, telles que [Start-Job](assetId:///2bc04935-0deb-4ec0-b856-d7290cca6442) et [Get-Job](assetId:///1352c534-7193-46ca-9ab1-0c5219a661ad).

À l’instar des tâches du Planificateur de tâches, vous pouvez exécuter des travaux planifiés selon une planification ponctuelle ou périodique, ou encore en réponse à une action ou à un événement. Vous pouvez afficher et gérer les travaux planifiés dans le Planificateur de tâches, les activer et les désactiver selon les besoins, les exécuter ou les utiliser en tant que modèles, et définir les conditions dans lesquelles ils démarrent.

Les travaux planifiés sont également fournis avec un ensemble personnalisé d'applets de commande permettant de les gérer. Les applets de commande vous permettent non seulement de créer, modifier, gérer, désactiver et réactiver des travaux planifiés, mais aussi de créer des déclencheurs et définir les options des travaux planifiés.

Pour plus d’informations sur les travaux planifiés, voir [about_Scheduled_Jobs](assetId:///3b546629-703c-4939-b44f-52dd567bce92).

### <a name="BKMK_Lang"></a>Rehaussement du langage Windows PowerShell
[!INCLUDE[psversion3](../Token/psversion3_md.md)] comprend de nombreuses fonctionnalités conçues non seulement pour simplifier le langage et le rendre plus convivial, mais aussi pour éviter les erreurs courantes. Parmi les améliorations apportées, citons l’énumération de propriétés, les propriétés count et length sur les objets scalaires, les nouveaux opérateurs de redirection, le modificateur de portée $Using, la variable automatique PSItem, le format de script flexible, les attributs des variables, la simplification des arguments d’attribut, les noms des commandes numériques, l’opérateur Stop-Parsing, la projection de tableau, de nouveaux opérateurs de bits, des dictionnaires ordonnés, le cast PSCustomObject et l’aide basée sur les commentaires.

### <a name="BKMK_Core"></a>Nouvelles applets de commande Core
De nouvelles applets de commande ont été ajoutées à l'installation de Windows PowerShell Core, notamment pour gérer les travaux planifiés, les sessions déconnectées, l'intégration CIM et le système d'aide actualisable.

|||
|-|-|
|Add-JobTrigger|New-JobTrigger|
|Connect-PSSession|New-PSSessionConfigurationFile|
|ConvertFrom-Json|New-PSTransportOption|
|ConvertTo-Json|New-PSWorkflowExecutionOption|
|Disable-JobTrigger|New-PSWorkflowSession|
|Disable-ScheduledJob|New-ScheduledJobOption|
|Disconnect-PSSession|New-WinEvent|
|Enable-JobTrigger|Receive-PSSession|
|Enable-ScheduledJob|Register-CimIndicationEvent|
|Get-CimAssociatedInstance|Register-ScheduledJob|
|Get-CimClass|Remove-CimInstance|
|Get-CimInstance|Remove-CimSession|
|Get-CimSession|Remove-TypeData|
|Get-ControlPanelItem|Rename-Computer|
|Get-IseSnippet|Resume-Job|
|Get-JobTrigger|Save-Help|
|Get-ScheduledJob|Set-CimInstance|
|Get-ScheduledJobOption|Set-JobTrigger|
|Get-TypeData|Set-ScheduledJob|
|Import-IseSnippet|Set-ScheduledJobOption|
|Invoke-AsWorkflow|Show-Command|
|Invoke-CimMethod|Show-ControlPanelItem|
|Invoke-RestMethod|Suspend-Job|
|Invoke-WebRequest|Test-PSSessionConfigurationFile|
|New-CimInstance|Unblock-File|
|New-CimSession|Unregister-ScheduledJob|
|New-CimSessionOption|Update-Help|
|New-IseSnippet||

### <a name="BKMK_Prov"></a>Améliorations apportées aux applets de commande et aux fournisseurs principaux existants
[!INCLUDE[psversion3](../Token/psversion3_md.md)] inclut de nouvelles fonctionnalités pour les applets de commande existantes, dont la syntaxe simplifiée et nouveaux paramètres pour les applets de commande suivantes : Computer, CSV, Get-ChildItem, Get-Command, Get-Content, Get-History, Measure-Object, Security, Select-Object, Select-String, Split-Path, Start-Process, Tee-Object, Test-Connection, Add-Member et WMI.

Les fournisseurs Windows PowerShell ont également bénéficié d'améliorations considérables. Citons notamment la prise en charge du fournisseur Certificate pour la gestion des certificats SSL (Secure Socket Layer) dans le cadre de l'hébergement web, la prise en charge des informations d'identification, les lecteurs réseau persistants et d'autres flux de données dans les lecteurs du système de fichiers.

### <a name="BKMK_REM"></a>Importation et découverte des modules à distance
[!INCLUDE[psversion3](../Token/psversion3_md.md)] étend aux ordinateurs distants les fonctionnalités de découverte de module, d’importation et de communication à distance de manière implicite. Les applets de commande Module obtiennent les modules sur les ordinateurs distants et les importent sur l'ordinateur distant ou local via la communication à distance Windows PowerShell. Grâce à la prise en charge des sessions CIM, vous pouvez utiliser CIM et WMI pour gérer des ordinateurs non Windows en important sur l’ordinateur local des commandes qui s’exécutent de manière implicite sur l’ordinateur distant.

Pour plus d’informations, consultez les rubriques d’aide relatives aux applets de commande [Get-Module](assetId:///2cccd4c4-9a21-4c77-b691-984ee57242e1) et [Import-Module](assetId:///af616c24-e122-4098-930e-1e3ea2080ade).

### <a name="BKMK_TAB"></a>Rehaussement de la saisie semi-automatique via la touche Tab
La saisie semi-automatique via la touche Tab dans la console [!INCLUDE[wps_2](../Token/wps_2_md.md)] permet désormais de terminer les noms d’applets de commande, de paramètres, de valeurs de paramètre, d’énumérations, de types .NET Framework, d’objets COM, de répertoires cachés, et bien plus. La fonctionnalité de saisie semi-automatique via la touche Tab a été entièrement réécrite. Elle repose désormais sur un nouvel analyseur et une nouvelle arborescence de syntaxe abstraite, qui prennent en charge davantage de scénarios, y compris les arborescences d’analyse en mémoire et la saisie semi-automatique via la touche Tab en milieu de ligne.

### <a name="BKMK_AutoLoad"></a>Chargement automatique des modules
L’applet de commande [Get-Command](assetId:///59c6d302-6e8c-48b7-a6f6-f0172df936ad) obtient désormais l’ensemble des applets de commande et des fonctions de tous les modules installés sur l’ordinateur, même si un module n’est pas importé dans la session active.

Quand vous obtenez l'applet de commande dont vous avez besoin, vous pouvez l'utiliser immédiatement sans importer de modules. Les modules de [!INCLUDE[mshshort](../Token/mshshort_md.md)] sont désormais importés automatiquement lorsque vous utilisez une applet de commande dans le module. Vous n'avez plus besoin de rechercher le module et de l'importer pour utiliser ses applets de commande.

Pour déclencher l’importation automatique des modules, utilisez l’applet de commande dans une commande, puis exécutez **Get-Command** pour une applet de commande sans caractères génériques ou [Get-Help](assetId:///1f46eeb4-49d7-4bec-bb29-395d9b42f54a) pour une applet de commande avec caractères génériques

Pour activer, désactiver et configurer l’importation automatique de modules, utilisez la variable de préférence **$PSModuleAutoLoadingPreference**.

Pour plus d’informations, voir [about_Modules [v4]](assetId:///94f57429-a539-4aee-bb0d-205cd7e801f9), [about_Preference_Variables [v4]](assetId:///31344314-be29-4286-b039-afa5460cbe8b) et les rubriques d’aide relatives aux applets de commande [Get-Command](assetId:///59c6d302-6e8c-48b7-a6f6-f0172df936ad) et [Import-Module](assetId:///af616c24-e122-4098-930e-1e3ea2080ade).

### <a name="BKMK_MOD"></a>Améliorations apportées aux fonctionnalités des modules
Dans Windows PowerShell 3.0, les modules prennent désormais en charge des fonctionnalités avancées, notamment les nouvelles fonctionnalités suivantes.

1.  Journalisation des modules individuels (LogPipelineExecutionDetails) et nouveau paramètre de stratégie de groupe « Activer l'enregistrement des modules ».

2.  Objets de module étendus qui exposent les valeurs à partir du manifeste de module.

3.  Nouvelle propriété **ExportedCommands** des modules, y compris les modules imbriqués, qui combine des commandes de tous types.

4.  Détection améliorée des modules disponibles (non importés), offrant notamment la possibilité d’utiliser les paramètres **Path** et **ListAvailable** dans la même commande.

5.  Nouvelle clé **DefaultCommandPrefix** dans les manifestes de module, qui évite les conflits de nom sans modifier le code du module.

6.  Amélioration des spécifications des modules, y compris les modules requis complets avec version et GUID et l’importation automatique des modules requis.

7.  Opération simplifiée et silencieuse de l’applet de commande [New-ModuleManifest](assetId:///512adced-f42f-4e88-ba7c-834fc9e5d047).

8.  Nouveau paramètre **Module** pour #Requires.

9. Amélioration de l’applet de commande [Import-Module](assetId:///af616c24-e122-4098-930e-1e3ea2080ade) avec les paramètres **MinimumVersion** et **RequiredVersion**.

### <a name="BKMK_SIMPLE"></a>Découverte des commandes simplifiée
Vous n'avez plus besoin d'importer tous les modules pour découvrir les commandes disponibles dans votre session. Dans [!INCLUDE[psversion3](../Token/psversion3_md.md)], l’applet de commande [Get-Command](assetId:///59c6d302-6e8c-48b7-a6f6-f0172df936ad) obtient toutes les commandes de tous les modules installés. Si vous utilisez une commande, le module qui exporte la commande est automatiquement importé dans votre session.

La nouvelle applet de commande [Show-Command](assetId:///65bba50b-91a8-49d5-80a2-a30fc684ba41) est conçue spécialement pour les débutants. Vous pouvez rechercher des commandes dans une fenêtre. Vous pouvez afficher toutes les commandes ou les filtrer par module, importer un module en cliquant sur un bouton, utiliser des zones de texte et des listes déroulantes pour construire une commande valide, puis copier ou exécuter la commande sans jamais quitter la fenêtre.

### <a name="BKMK_LOG"></a>Prise en charge améliorée de la journalisation, des diagnostics et de la stratégie de groupe
[!INCLUDE[psversion3](../Token/psversion3_md.md)] améliore la prise en charge de la journalisation et du suivi pour les commandes et les modules. Il prend également en charge les journaux de suivi d’événements pour Windows (ETW), une propriété **LogPipelineExecutionDetails** modifiable des modules, ainsi que le paramètre de stratégie de groupe « Activer l’enregistrement des modules ». Vous pouvez désormais obtenir les valeurs de paramètres à partir des détails du journal en affichant les propriétés du journal.

### <a name="BKMK_OUT"></a>Améliorations apportées à la mise en forme et à la sortie
Les améliorations apportées à la mise en forme et à la sortie permettent d’accroître la productivité de tous les utilisateurs de [!INCLUDE[wps_2](../Token/wps_2_md.md)]. Parmi ces améliorations, citons la redirection de la sortie de tous les flux, une applet de commande Update-Type améliorée qui ajoute dynamiquement des types sans les fichiers Format.ps1xml, le retour automatique à la ligne de la sortie, les propriétés de mise en forme par défaut des objets personnalisés, le type **PSCustomObject**, la mise en forme améliorée des objets WMI et des objets hétérogènes, ainsi que la prise en charge de la découverte des surcharges de méthode.

### <a name="BKMK_HOST"></a>Améliorations apportées aux fonctionnalités de l’hôte de console
Le programme hôte de la console [!INCLUDE[wps_2](../Token/wps_2_md.md)] comprend de nouvelles fonctionnalités disponibles dans [!INCLUDE[psversion3](../Token/psversion3_md.md)], dont un thread unique cloisonné par défaut. La nouvelle option « Exécuter avec PowerShell » dans l’Explorateur de fichiers permet d’exécuter des scripts dans une session non restreinte d’un simple clic droit. La nouvelle logique de lancement de l'hôte de la console démarre Windows PowerShell plus rapidement, et de nouvelles polices vous permettent de personnaliser l'expérience dans la fenêtre de la console.

Pour plus d’informations, voir [about_Run_With_PowerShell](assetId:///c9d9ca5f-eff9-4409-be9d-e43b5b4087eb).

### <a name="BKMK_API"></a>Nouvelles API Cmdlet et Hosting
Les nouvelles API Cmdlet et Hosting incluent des API d'arborescence de syntaxe avancée publiques, ainsi que des API pour la pagination des pipelines, les pipelines imbriqués, la saisie semi-automatique par tabulation des pools d'instance d'exécution, Windows RT, l'attribut d'applet de commande Obsolete et les propriétés Verb et Noun de l'objet FunctionInfo.

### <a name="BKMK_PERF"></a>Améliorations apportées aux performances
Les gains importants en termes de performances dans Windows PowerShell proviennent du nouvel analyseur de langage, qui repose sur Dynamic Runtime Language (DLR) dans .NET Framework 4., mais aussi de la compilation des scripts au moment de l’exécution, des améliorations en matière de fiabilité du moteur et des modifications apportées à l’algorithme de l’applet de commande [Get-ChildItem](assetId:///75cf79bb-4db6-4a67-8c36-3d20754e2190). Tout cela contribue à l’amélioration des performances de Windows PowerShell, en particulier lors de la recherche sur des partages réseau.

### <a name="BKMK_RUNAS"></a>Prise en charge de RunAs et de SharedHost
[!INCLUDE[psversion3](../Token/psversion3_md.md)] prend en charge les fonctionnalités RunAs et SharedHost.

La fonctionnalité *RunAs*, conçue pour le flux de travail Windows PowerShell, permet aux utilisateurs d’une configuration de session de créer des sessions qui s’exécutent avec l’autorisation d’un compte d’utilisateur partagé. Elle permet aux utilisateurs moins privilégiés d'exécuter des commandes et des scripts particuliers avec des autorisations d'administrateur, ce qui évite l'ajout d'utilisateurs expérimentés au groupe Administrateurs.

Grâce à la fonctionnalité **SharedHost**, plusieurs utilisateurs sur différents ordinateurs peuvent se connecter simultanément à une session de flux de travail et surveiller sa progression. Les utilisateurs peuvent démarrer un flux de travail sur un ordinateur, puis se connecter à la session de flux de travail sur un autre ordinateur sans déconnecter la session de l'ordinateur d'origine. Les utilisateurs doivent avoir les mêmes autorisations et utiliser la même configuration de session. Pour plus d'informations, consultez « Exécution d'un flux de travail Windows PowerShell » dans Prise en main de Windows PowerShell Workflow.

### <a name="BKMK_CHAR"></a>Améliorations apportées à la gestion des caractères spéciaux
Pour améliorer l’interprétation et la gestion des caractères spéciaux dans [!INCLUDE[psversion3](../Token/psversion3_md.md)], le paramètre **LiteralPath**, qui gère les caractères spéciaux dans les chemins d’accès, est valide sur pratiquement toutes les applets de commande possédant un paramètre **Path**, dont les nouvelles applets de commande [Update-Help](assetId:///93e1d870-ace6-432b-8778-8920291d7545) et [Save-Help](assetId:///aed94f90-b73f-4e25-a25d-7c18d9f161fa). L’analyseur inclut également une logique spéciale qui améliore la gestion de l’accent grave (`) et des crochets dans les chemins d’accès et les noms de fichiers.

## Voir aussi
[about_Windows_PowerShell_4.0](http://technet.microsoft.com/en-us/library/hh847833(v=wps.630).aspx)
[about_Windows_PowerShell_5.0](assetId:///6d56fa88-371e-40c9-b2de-64a2a0cd49da)
[Windows PowerShell](http://go.microsoft.com/fwlink/?LinkID=107116)



<!--HONumber=Apr16_HO1-->

