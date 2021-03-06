---
title: Ressource User dans DSC
ms.date: 2016-05-16
keywords: powershell,DSC
description: 
ms.topic: article
author: eslesar
manager: dongill
ms.prod: powershell
translationtype: Human Translation
ms.sourcegitcommit: 6477ae8575c83fc24150f9502515ff5b82bc8198
ms.openlocfilehash: 5c7878bdfc8a3f118b569a9e43be6c7e4333ad2c

---

#Ressource User dans DSC#

 
>S’applique à : Windows PowerShell 4.0, Windows PowerShell 5.0


La ressource __User__ dans la configuration d’état souhaité (DSC) Windows PowerShell fournit un mécanisme pour gérer des comptes d’utilisateur locaux sur le nœud cible.


##Syntaxe##

```
User [string] #ResourceName
{
    UserName = [string]
    [ Description = [string] ]
    [ Disabled = [bool] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ FullName = [string] ]
    [ Password = [PSCredential] ]
    [ PasswordChangeNotAllowed = [bool] ]
    [ PasswordChangeRequired = [bool] ]
    [ PasswordNeverExpires = [bool] ]
    [ DependsOn = [string[]] ]
}
```

## Propriétés
|  Propriété  |  Description   | 
|---|---| 
| UserName| Indique le nom du compte pour lequel vous voulez garantir un état spécifique.| 
| Description| Indique la description que vous voulez utiliser pour le compte d’utilisateur.| 
| Désactivé| Indique si le compte est activé. Définissez cette propriété sur __$true__ pour vous assurer que ce compte est désactivé, ou sur __$false__ pour vous assurer qu’il est activé.| 
| Ensure| Indique si le compte existe. Définissez cette propriété sur « Present » pour vous assurer que le compte existe, ou sur « Absent » pour vous assurer que le compte n’existe pas.| 
| FullName| Représente une chaîne avec le nom complet que vous voulez utiliser pour le compte d’utilisateur.| 
| Password| Indique le mot de passe que vous voulez utiliser pour ce compte. | 
| PasswordChangeNotAllowed| Indique si l’utilisateur peut modifier le mot de passe. Définissez cette propriété sur __$true__ pour vous assurer que l’utilisateur ne modifie pas le mot de passe, ou sur __$false__ pour permettre à l’utilisateur de modifier le mot de passe. La valeur par défaut est __$false__.| 
| PasswordChangeRequired| Indique si l’utilisateur doit changer de mot de passe à la prochaine connexion. Définissez cette propriété sur __$true__ si l’utilisateur doit changer le mot de passe. La valeur par défaut est __$true__.| 
| PasswordNeverExpires| Indique si le mot de passe doit expirer. Pour vous assurer que le mot de passe pour ce compte n’expire jamais, définissez cette propriété sur __$true__, et sur __$false__ si le mot de passe doit expirer. La valeur par défaut est __$false__.| 
| DependsOn | Indique que la configuration d’une autre ressource doit être exécutée avant celle de cette ressource. Par exemple, si vous voulez exécuter en premier le bloc de script de configuration de ressource __ResourceName__ de type __ResourceType__, la syntaxe permettant d’utiliser cette propriété est `DependsOn = "[ResourceType]ResourceName"`.| 

## Exemple

```powershell
User UserExample
{
    Ensure = "Present"  # To ensure the user account does not exist, set Ensure to "Absent"
    UserName = "SomeName"
    Password = $passwordCred # This needs to be a credential object
    DependsOn = “[Group]GroupExample" # Configures GroupExample first
}
```




<!--HONumber=Jun16_HO4-->


