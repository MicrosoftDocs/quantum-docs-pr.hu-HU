---
title: 'Matematika a Q # standard könyvtárakban'
description: 'Ismerkedjen meg a beépített adattípusokkal használt Q # standard szintű kódtárak klasszikus matematikai funkcióival.'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274957"
---
# <a name="classical-mathematical-functions"></a>Klasszikus matematikai függvények #

Ezek a függvények elsődlegesen a Q # beépített adattípusokkal, és a használatával `Int` működnek `Double` `Range` .

A <xref:microsoft.quantum.intrinsic.random> művelet aláírása `(Double[] => Int)` .
A rendszer a számok tömbjét veszi fel bemenetként, és egy véletlenszerűen kiválasztott indexet ad vissza a tömbben `Int` .
Egy adott index kiválasztásának valószínűsége az adott indexben lévő tömb elem értékével arányos. a nullánál kisebb tömb elemek figyelmen kívül lesznek hagyva, és a rendszer soha nem adja vissza az indexeket.
Ha bármely tömb elem nullánál kisebb, vagy ha egy tömb elem nem nullánál nagyobb, akkor a művelet meghiúsul.
