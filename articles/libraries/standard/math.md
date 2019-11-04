---
title: 'Q # standard könyvtárak – matematika | Microsoft Docs'
description: 'Q # standard könyvtárak – matematika'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 7ac9d321f59f7cc95ad8939a4cf7c36e0c5e0491
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184457"
---
# <a name="classical-mathematical-functions"></a>Klasszikus matematikai függvények #

Ezek a függvények elsősorban a Q # beépített adattípusok használatával működnek, `Int`, `Double`és `Range`.

A <xref:microsoft.quantum.intrinsic.random> művelet aláírása `(Double[] => Int)`.
A rendszer a számok tömbjét veszi fel bemenetként, és egy véletlenszerűen kiválasztott indexet ad vissza a tömbben `Int`ként.
Egy adott index kiválasztásának valószínűsége az adott indexben lévő tömb elem értékével arányos. a nullánál kisebb tömb elemek figyelmen kívül lesznek hagyva, és a rendszer soha nem adja vissza az indexeket.
Ha bármely tömb elem nullánál kisebb, vagy ha egy tömb elem nem nullánál nagyobb, akkor a művelet meghiúsul.