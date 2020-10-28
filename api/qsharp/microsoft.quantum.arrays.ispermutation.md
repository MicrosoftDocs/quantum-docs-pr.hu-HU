---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719105"
---
# <a name="ispermutation-function"></a><span data-ttu-id="92018-102">IsPermutation függvény</span><span class="sxs-lookup"><span data-stu-id="92018-102">IsPermutation function</span></span>

<span data-ttu-id="92018-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="92018-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="92018-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="92018-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="92018-105">Igaz értéket ad eredményül, ha a megadott tömb egy permutációt jelöl.</span><span class="sxs-lookup"><span data-stu-id="92018-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="92018-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="92018-106">Description</span></span>

<span data-ttu-id="92018-107">A `array` Hossz `n` függvényében az igaz értéket adja vissza, és csak akkor, ha a és a közötti egész szám `0` `n - 1` pontosan egyszer jelenik meg a (z)-ben `array` , így az `array` elemek esetében permutációként is értelmezhető `n` .</span><span class="sxs-lookup"><span data-stu-id="92018-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="92018-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="92018-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="92018-109">permuation: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="92018-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="92018-110">Egy olyan tömb, amely lehet, hogy nem egy permutációt jelöl.</span><span class="sxs-lookup"><span data-stu-id="92018-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="92018-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="92018-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="remarks"></a><span data-ttu-id="92018-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="92018-112">Remarks</span></span>

<span data-ttu-id="92018-113">A nulla hosszúságú tömb triviálisan egy permutáció.</span><span class="sxs-lookup"><span data-stu-id="92018-113">An array of length zero is trivially a permutation.</span></span>