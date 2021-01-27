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
# <a name="classical-mathematical-functions"></a><span data-ttu-id="4e26b-103">Klasszikus matematikai függvények</span><span class="sxs-lookup"><span data-stu-id="4e26b-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="4e26b-104">Ezeket a függvényeket elsősorban a Q# beépített adattípusokkal, és a szolgáltatással való együttműködésre használják `Int` `Double` `Range` .</span><span class="sxs-lookup"><span data-stu-id="4e26b-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="4e26b-105">A <xref:Microsoft.Quantum.Intrinsic.Random> művelet aláírása `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="4e26b-105">The <xref:Microsoft.Quantum.Intrinsic.Random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="4e26b-106">A rendszer a számok tömbjét veszi fel bemenetként, és egy véletlenszerűen kiválasztott indexet ad vissza a tömbben `Int` .</span><span class="sxs-lookup"><span data-stu-id="4e26b-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="4e26b-107">Egy adott index kiválasztásának valószínűsége az adott indexben lévő tömb elem értékével arányos.</span><span class="sxs-lookup"><span data-stu-id="4e26b-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="4e26b-108">a nullánál kisebb tömb elemek figyelmen kívül lesznek hagyva, és a rendszer soha nem adja vissza az indexeket.</span><span class="sxs-lookup"><span data-stu-id="4e26b-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="4e26b-109">Ha bármely tömb elem nullánál kisebb, vagy ha egy tömb elem nem nullánál nagyobb, akkor a művelet meghiúsul.</span><span class="sxs-lookup"><span data-stu-id="4e26b-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
