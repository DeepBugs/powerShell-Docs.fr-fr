---
title: MSFT_DSCLocalConfigurationManager, classe
ms.date: 2016-05-16
keywords: powershell,DSC
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
translationtype: Human Translation
ms.sourcegitcommit: 26db4a48af3aa3d6a9a2054fb85da8779626f284
ms.openlocfilehash: b9cb89bb120151df69e3cb26b50c3a0d15c23711

---

# MSFT_DSCLocalConfigurationManager, classe

Gestionnaire de configuration local qui contrôle les états des fichiers de configuration et utilise l’agent de configuration pour appliquer les configurations.

La syntaxe suivante est simplifiée par rapport au code MOF (Managed Object Format) et inclut toutes les propriétés héritées.

## Syntaxe
------

``` syntax
[ClassVersion("1.0.0"), dynamic, provider("dsccore"), AMENDMENT]
class MSFT_DSCLocalConfigurationManager
{
};
```

## Membres
-------

La classe **MSFT_DSCLocalConfigurationManager** comprend les membres suivants :

-   [Méthodes][]

### Méthodes

La classe **MSFT_DSCLocalConfigurationManager** comprend les méthodes suivantes.

|Méthode |Description |
|:--- |:---|
| [ApplyConfiguration](msft-dsclocalconfigurationmanager-applyconfiguration.md)| Utilise l’agent de configuration pour appliquer la configuration en attente.| 
| [DisableDebugConfiguration](msft-dsclocalconfigurationmanager-disabledebugconfiguration.md)| Désactive le débogage des ressources DSC.| 
| [EnableDebugConfiguration](msft-dsclocalconfigurationmanager-enabledebugconfiguration.md)| Active le débogage des ressources DSC.| 
| [GetConfiguration](msft-dsclocalconfigurationmanager-getconfiguration.md)| Envoie le document de configuration au nœud géré et utilise la méthode **Get** de l’agent de configuration pour appliquer la configuration.| 
| [GetConfigurationResultOutput](msft-dsclocalconfigurationmanager-getconfigurationresultoutput.md)| Obtient la sortie de l’agent de configuration associée à un travail spécifique.| 
| [GetConfigurationStatus](msft-dsclocalconfigurationmanager-getconfigurationstatus.md)| Obtenez l’historique des états de la configuration.| 
| [GetMetaConfiguration](msft-dsclocalconfigurationmanager-getmetaconfiguration.md)| Obtient les paramètres du Gestionnaire de configuration local qui permettent de contrôler l’agent de configuration.| 
| [PerformRequiredConfigurationChecks](msft-dsclocalconfigurationmanager-performrequiredconfigurationchecks.md)| Démarre la vérification de cohérence.| 
| [RemoveConfiguration](msft-dsclocalconfigurationmanager-removeconfiguration.md)| Supprime les fichiers de configuration.| 
| [ResourceGet](msft-dsclocalconfigurationmanager-resourceget.md)| Appelle directement la méthode **Get** d’une ressource DSC.| 
| [ResourceSet](msft-dsclocalconfigurationmanager-resourceset.md)| Appelle directement la méthode **Set** d’une ressource DSC.| 
| [ResourceTest](msft-dsclocalconfigurationmanager-resourcetest.md)| Appelle directement la méthode **Test** d’une ressource DSC.| 
| [RollBack](msft-dsclocalconfigurationmanager-rollback.md)| Restaure une configuration précédente.| 
| [SendConfiguration](msft-dsclocalconfigurationmanager-sendconfiguration.md)| Envoie le document de configuration au nœud géré et l’enregistre comme une modification en attente.| 
| [SendConfigurationApply](msft-dsclocalconfigurationmanager-sendconfigurationapply.md)| Envoie le document de configuration au nœud géré et utilise l’agent de configuration pour appliquer la configuration.| 
| [SendConfigurationApplyAsync](msft-dsclocalconfigurationmanager-sendconfigurationapplyasync.md)| Envoyez le document de configuration au nœud géré et commencez à utiliser l’agent de configuration pour appliquer la configuration. Utilisez GetConfigurationResultOutput pour récupérer la sortie du résultat.| 
| [SendMetaConfigurationApply](msft-dsclocalconfigurationmanager-sendmetaconfigurationapply.md)| Définit les paramètres du Gestionnaire de configuration local qui permettent de contrôler l’agent de configuration.| 
| [StopConfiguration](msft-dsclocalconfigurationmanager-stopconfiguration.md)| Arrête la configuration en cours.| 
| [TestConfiguration](msft-dsclocalconfigurationmanager-testconfiguration.md)| Envoie le document de configuration au nœud géré et vérifie la configuration actuelle par rapport au document.| 



 

## Spécifications
------------
>**MOF :** DscCore.mof

>**Espace de noms** : Root\Microsoft\Windows\DesiredStateConfiguration



 

 






<!--HONumber=Jun16_HO4-->


