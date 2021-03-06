---
title: "Pipeline d’objet"
ms.date: 2016-05-11
keywords: powershell,applet de commande
description: 
ms.topic: article
author: jpjofre
manager: dongill
ms.prod: powershell
ms.assetid: 523d8ae4-d743-47a4-b79a-806130ca688a
translationtype: Human Translation
ms.sourcegitcommit: 3222a0ba54e87b214c5ebf64e587f920d531956a
ms.openlocfilehash: 7f4cafad8854c19f733a2672ba6b40834d93aac0

---

# Pipeline d’objet
Les pipelines agissent comme une série de segments de canal connectés. Les éléments se déplaçant dans pipeline passent par chaque segment. Pour créer un pipeline dans Windows PowerShell, vous interconnectez des commandes à l’aide que l’opérateur barre verticale « | » (pipe). La sortie de chaque commande est utilisée en tant qu’entrée pour la commande suivante.

Les pipelines constituent indubitablement le concept plus important utilisé dans les interfaces de ligne de commande. Correctement utilisés, les pipelines non seulement réduisent l’effort que nécessite la saisie de commandes complexes, mais aussi facilitent l’affichage du flux de travail dans les commandes. Une caractéristique utile connexe des pipelines est que, comme ils opèrent sur chaque élément séparément, vous n’avez pas à les modifier selon qu’ils contiennent zéro, un ou plusieurs éléments. En outre, chaque commande dans un pipeline (appelée élément de pipeline) transmet généralement sa sortie à la commande suivante, élément par élément. Généralement, cela réduit la demande de ressources de commandes complexes, et permet de commencer à recevoir la sortie immédiatement.

Dans ce chapitre, nous expliquons en quoi le pipeline Windows PowerShell diffère des pipelines des interpréteurs de commandes les plus populaires, puis présentons des outils de base que vous pouvez utiliser pour contrôler la sortie du pipeline et voir comment celui-ci fonctionne.




<!--HONumber=Aug16_HO4-->


