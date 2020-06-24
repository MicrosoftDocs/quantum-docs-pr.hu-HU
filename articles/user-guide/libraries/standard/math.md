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
# <a name="classical-mathematical-functions"></a><span data-ttu-id="f9c5e-103">Klasszikus matematikai függvények</span><span class="sxs-lookup"><span data-stu-id="f9c5e-103">Classical Mathematical Functions</span></span> #

<span data-ttu-id="f9c5e-104">Ezek a függvények elsődlegesen a Q # beépített adattípusokkal, és a használatával `Int` működnek `Double` `Range` .</span><span class="sxs-lookup"><span data-stu-id="f9c5e-104">These functions are primarily used to work with the Q# built-in data types `Int`, `Double`, and `Range`.</span></span>

<span data-ttu-id="f9c5e-105">A <xref:microsoft.quantum.intrinsic.random> művelet aláírása `(Double[] => Int)` .</span><span class="sxs-lookup"><span data-stu-id="f9c5e-105">The <xref:microsoft.quantum.intrinsic.random> operation has signature `(Double[] => Int)`.</span></span>
<span data-ttu-id="f9c5e-106">A rendszer a számok tömbjét veszi fel bemenetként, és egy véletlenszerűen kiválasztott indexet ad vissza a tömbben `Int` .</span><span class="sxs-lookup"><span data-stu-id="f9c5e-106">It takes an array of doubles as input, and returns a randomly-selected index into the array as an `Int`.</span></span>
<span data-ttu-id="f9c5e-107">Egy adott index kiválasztásának valószínűsége az adott indexben lévő tömb elem értékével arányos.</span><span class="sxs-lookup"><span data-stu-id="f9c5e-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span> <span data-ttu-id="f9c5e-108">a nullánál kisebb tömb elemek figyelmen kívül lesznek hagyva, és a rendszer soha nem adja vissza az indexeket.</span><span class="sxs-lookup"><span data-stu-id="f9c5e-108">n Array elements that are equal to zero are ignored and their indices are never returned.</span></span>
<span data-ttu-id="f9c5e-109">Ha bármely tömb elem nullánál kisebb, vagy ha egy tömb elem nem nullánál nagyobb, akkor a művelet meghiúsul.</span><span class="sxs-lookup"><span data-stu-id="f9c5e-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>
