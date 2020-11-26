---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 144f683818b5d75de5b075328365d3e994de29d1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220926"
---
# <a name="ispermutation-function"></a><span data-ttu-id="acf6d-102">IsPermutation függvény</span><span class="sxs-lookup"><span data-stu-id="acf6d-102">IsPermutation function</span></span>

<span data-ttu-id="acf6d-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="acf6d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="acf6d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="acf6d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="acf6d-105">Igaz értéket ad eredményül, ha a megadott tömb egy permutációt jelöl.</span><span class="sxs-lookup"><span data-stu-id="acf6d-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="acf6d-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="acf6d-106">Description</span></span>

<span data-ttu-id="acf6d-107">A `array` Hossz `n` függvényében az igaz értéket adja vissza, és csak akkor, ha a és a közötti egész szám `0` `n - 1` pontosan egyszer jelenik meg a (z)-ben `array` , így az `array` elemek esetében permutációként is értelmezhető `n` .</span><span class="sxs-lookup"><span data-stu-id="acf6d-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="acf6d-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="acf6d-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="acf6d-109">permuation: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="acf6d-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="acf6d-110">Egy olyan tömb, amely lehet, hogy nem egy permutációt jelöl.</span><span class="sxs-lookup"><span data-stu-id="acf6d-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="acf6d-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="acf6d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="remarks"></a><span data-ttu-id="acf6d-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="acf6d-112">Remarks</span></span>

<span data-ttu-id="acf6d-113">A nulla hosszúságú tömb triviálisan egy permutáció.</span><span class="sxs-lookup"><span data-stu-id="acf6d-113">An array of length zero is trivially a permutation.</span></span>