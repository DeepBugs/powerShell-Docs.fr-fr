---
title: Ressource Package dans DSC
ms.date: 2016-05-16
keywords: powershell,DSC
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
translationtype: Human Translation
ms.sourcegitcommit: 62f993e3d3e6ef744fb07920d332d476dfd24fc6
ms.openlocfilehash: d07b11c148dfa747b3f9c0157191b83efb6c65df

---

# Ressource Package dans DSC

> S’applique à : Windows PowerShell 4.0, Windows PowerShell 5.0

La ressource **Package** dans DSC Windows PowerShell fournit un mécanisme permettant d’installer ou de désinstaller des packages, tels que les packages Windows Installer et setup.exe, sur un nœud cible.

## Syntaxe

```
Package [string] #ResourceName
{
    Name = [string]
    Path = [string]
    ProductId = [string]
    [ Arguments = [string] ]
    [ Credential = [PSCredential] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ ReturnCode = [UInt32[]] ]
}
```

## Propriétés
|  Propriété  |  Description   | 
|---|---| 
| Name| Indique le nom du package pour lequel vous souhaitez garantir un état spécifique.| 
| Path| Indique le chemin où se trouve le package.| 
| ProductId| Indique l’ID de produit qui identifie le package de manière unique.| 
| Arguments| Chaîne d’arguments transmise telle quelle au package.| 
| Credential| Informations d’identification permettant l’accès au package sur une source distante. Cette propriété n’est pas utilisée pour installer le package. Le package est toujours installé sur le système local.| 
| Ensure| Indique si le package est installé. Définissez cette propriété sur « Absent » pour vous assurer que le package n’est pas installé (ou désinstallé, si le package n’est pas installé). Définissez cette propriété sur « Present » (valeur par défaut) pour vous assurer que le package est installé.| 
| LogPath| Indique le chemin complet où vous souhaitez que le fournisseur enregistre un fichier journal pour installer ou désinstaller le package.| 
| DependsOn | Indique que la configuration d’une autre ressource doit être exécutée avant celle de cette ressource. Par exemple, si vous voulez exécuter en premier le bloc de script de configuration de ressource ayant l’ID **ResourceName** et le type **ResourceType**, utilisez la syntaxe suivante pour cette propriété : DependsOn = "[ResourceType]ResourceName"| 
| ReturnCode| Indique le code de retour attendu. Si le code de retour réel ne correspond pas à la valeur attendue indiquée ici, la configuration retourne une erreur.| 

## Exemple

Cet exemple exécute le programme d’installation .msi qui se trouve dans le chemin spécifié et qui possède l’ID de produit spécifié.

```powershell
Configuration PackageTest
{
    Package PackageExample
    {
        Ensure      = "Present"  # You can also set Ensure to "Absent"
        Path        = "$Env:SystemDrive\TestFolder\TestProject.msi"
        Name        = "TestPackage"
        ProductId   = "ACDDCDAF-80C6-41E6-A1B9-8ABD8A05027E"
    } 
}
```




<!--HONumber=Sep16_HO3-->


