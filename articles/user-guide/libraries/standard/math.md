---
title: 'Matematikai a Q# standard könyvtárakban'
description: 'Ismerje meg a Q# beépített adattípusokkal használt szabványos kódtárak klasszikus matematikai funkcióit.'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad
ms.topic: article
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 6de1574341d67c569cd2f040ec533e263fdd386e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692061"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="a8ccc-103">Klasszikus matematikai függvények</span><span class="sxs-lookup"><span data-stu-id="a8ccc-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="a8ccc-104">Ezeket a függvényeket elsősorban a Q# beépített adattípusokkal, és a szolgáltatással való együttműködésre használják `Int` `Double` `Range` .</span><span class="sxs-lookup"><span data-stu-id="a8ccc-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="a8ccc-105">A <xref:Microsoft.Quantum.Intrinsic.Random> művelet aláírása `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="a8ccc-105">The <xref:Microsoft.Quantum.Intrinsic.Random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="a8ccc-106">A rendszer a számok tömbjét veszi fel bemenetként, és egy véletlenszerűen kiválasztott indexet ad vissza a tömbben `Int` .</span><span class="sxs-lookup"><span data-stu-id="a8ccc-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="a8ccc-107">Egy adott index kiválasztásának valószínűsége az adott indexben lévő tömb elem értékével arányos.</span><span class="sxs-lookup"><span data-stu-id="a8ccc-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="a8ccc-108">a nullánál kisebb tömb elemek figyelmen kívül lesznek hagyva, és a rendszer soha nem adja vissza az indexeket.</span><span class="sxs-lookup"><span data-stu-id="a8ccc-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="a8ccc-109">Ha bármely tömb elem nullánál kisebb, vagy ha egy tömb elem nem nullánál nagyobb, akkor a művelet meghiúsul.</span><span class="sxs-lookup"><span data-stu-id="a8ccc-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
