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
ms.openlocfilehash: 6de1574341d67c569cd2f040ec533e263fdd386e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692061"
---
# <a name="classical-mathematical-functions"></a>Klasszikus matematikai függvények #

Ezeket a függvényeket elsősorban a Q# beépített adattípusokkal, és a szolgáltatással való együttműködésre használják `Int` `Double` `Range` .

A <xref:Microsoft.Quantum.Intrinsic.Random> művelet aláírása `(Double[] => Int)` .
A rendszer a számok tömbjét veszi fel bemenetként, és egy véletlenszerűen kiválasztott indexet ad vissza a tömbben `Int` .
Egy adott index kiválasztásának valószínűsége az adott indexben lévő tömb elem értékével arányos. a nullánál kisebb tömb elemek figyelmen kívül lesznek hagyva, és a rendszer soha nem adja vissza az indexeket.
Ha bármely tömb elem nullánál kisebb, vagy ha egy tömb elem nem nullánál nagyobb, akkor a művelet meghiúsul.
