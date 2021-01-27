---
title: Matematikai a Q# standard könyvtárakban
description: Ismerje meg a Q# beépített adattípusokkal használt szabványos kódtárak klasszikus matematikai funkcióit.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: a2e2656f42213c8ae9e984f63f3ebf4058520532
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853998"
---
# <a name="classical-mathematical-functions"></a>Klasszikus matematikai függvények #

Ezeket a függvényeket elsősorban a Q# beépített adattípusokkal, és a szolgáltatással való együttműködésre használják `Int` `Double` `Range` .

A <xref:Microsoft.Quantum.Intrinsic.Random> művelet aláírása `(Double[] => Int)` .
A rendszer a számok tömbjét veszi fel bemenetként, és egy véletlenszerűen kiválasztott indexet ad vissza a tömbben `Int` .
Egy adott index kiválasztásának valószínűsége az adott indexben lévő tömb elem értékével arányos. a nullánál kisebb tömb elemek figyelmen kívül lesznek hagyva, és a rendszer soha nem adja vissza az indexeket.
Ha bármely tömb elem nullánál kisebb, vagy ha egy tömb elem nem nullánál nagyobb, akkor a művelet meghiúsul.
