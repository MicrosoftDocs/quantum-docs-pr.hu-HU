---
title: Matematikai a Q# standard könyvtárakban
description: Ismerje meg a Q# beépített adattípusokkal használt szabványos kódtárak klasszikus matematikai funkcióit.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 55b1ef70eed1eb47ab0c6b30e2b8203c38c9a67a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833597"
---
# <a name="classical-mathematical-functions"></a>Klasszikus matematikai függvények #

Ezeket a függvényeket elsősorban a Q# beépített adattípusokkal, és a szolgáltatással való együttműködésre használják `Int` `Double` `Range` .

A <xref:microsoft.quantum.intrinsic.random> művelet aláírása `(Double[] => Int)` .
A rendszer a számok tömbjét veszi fel bemenetként, és egy véletlenszerűen kiválasztott indexet ad vissza a tömbben `Int` .
Egy adott index kiválasztásának valószínűsége az adott indexben lévő tömb elem értékével arányos. a nullánál kisebb tömb elemek figyelmen kívül lesznek hagyva, és a rendszer soha nem adja vissza az indexeket.
Ha bármely tömb elem nullánál kisebb, vagy ha egy tömb elem nem nullánál nagyobb, akkor a művelet meghiúsul.
