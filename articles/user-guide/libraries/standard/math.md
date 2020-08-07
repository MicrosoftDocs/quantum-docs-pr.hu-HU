---
title: Matematikai a Q# standard könyvtárakban
description: Ismerje meg a Q# beépített adattípusokkal használt szabványos kódtárak klasszikus matematikai funkcióit.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4a3747eaa2c91e482ded3af1279a0e40d922bfb3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868423"
---
# <a name="classical-mathematical-functions"></a><span data-ttu-id="20331-103">Klasszikus matematikai függvények</span><span class="sxs-lookup"><span data-stu-id="20331-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="20331-104">Ezeket a függvényeket elsősorban a Q# beépített adattípusokkal, és a szolgáltatással való együttműködésre használják `Int` `Double` `Range` .</span><span class="sxs-lookup"><span data-stu-id="20331-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="20331-105">A <xref:microsoft.quantum.intrinsic.random> művelet aláírása `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="20331-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="20331-106">A rendszer a számok tömbjét veszi fel bemenetként, és egy véletlenszerűen kiválasztott indexet ad vissza a tömbben `Int` .</span><span class="sxs-lookup"><span data-stu-id="20331-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="20331-107">Egy adott index kiválasztásának valószínűsége az adott indexben lévő tömb elem értékével arányos.</span><span class="sxs-lookup"><span data-stu-id="20331-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="20331-108">a nullánál kisebb tömb elemek figyelmen kívül lesznek hagyva, és a rendszer soha nem adja vissza az indexeket.</span><span class="sxs-lookup"><span data-stu-id="20331-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="20331-109">Ha bármely tömb elem nullánál kisebb, vagy ha egy tömb elem nem nullánál nagyobb, akkor a művelet meghiúsul.</span><span class="sxs-lookup"><span data-stu-id="20331-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
