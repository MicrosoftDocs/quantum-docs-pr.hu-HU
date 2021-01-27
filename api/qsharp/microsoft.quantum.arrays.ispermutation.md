---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848098"
---
# <a name="ispermutation-function"></a><span data-ttu-id="79fde-102">IsPermutation függvény</span><span class="sxs-lookup"><span data-stu-id="79fde-102">IsPermutation function</span></span>

<span data-ttu-id="79fde-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="79fde-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="79fde-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="79fde-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="79fde-105">Igaz értéket ad eredményül, ha a megadott tömb egy permutációt jelöl.</span><span class="sxs-lookup"><span data-stu-id="79fde-105">Outputs true if and only if a given array represents a permutation.</span></span>

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a><span data-ttu-id="79fde-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="79fde-106">Description</span></span>

<span data-ttu-id="79fde-107">A `array` Hossz `n` függvényében az igaz értéket adja vissza, és csak akkor, ha a és a közötti egész szám `0` `n - 1` pontosan egyszer jelenik meg a (z)-ben `array` , így az `array` elemek esetében permutációként is értelmezhető `n` .</span><span class="sxs-lookup"><span data-stu-id="79fde-107">Given an array `array` of length `n`, returns true if and only if each integer from `0` to `n - 1` appears exactly once in `array`, such that `array` can be interpreted as a permutation on `n` elements.</span></span>

## <a name="input"></a><span data-ttu-id="79fde-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="79fde-108">Input</span></span>

### <a name="permuation--int"></a><span data-ttu-id="79fde-109">permuation: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="79fde-109">permuation : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="79fde-110">Egy olyan tömb, amely lehet, hogy nem egy permutációt jelöl.</span><span class="sxs-lookup"><span data-stu-id="79fde-110">An array that may or may not represent a permutation.</span></span>



## <a name="output--bool"></a><span data-ttu-id="79fde-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="79fde-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="example"></a><span data-ttu-id="79fde-112">Példa</span><span class="sxs-lookup"><span data-stu-id="79fde-112">Example</span></span>

<span data-ttu-id="79fde-113">A következő Q # kód kinyomtatja az "összes diagnosztika sikeresen befejeződött" üzenetet:</span><span class="sxs-lookup"><span data-stu-id="79fde-113">The following Q# code prints the message "All diagnostics completed successfully":</span></span>

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a><span data-ttu-id="79fde-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="79fde-114">Remarks</span></span>

<span data-ttu-id="79fde-115">A nulla hosszúságú tömb triviálisan egy permutáció.</span><span class="sxs-lookup"><span data-stu-id="79fde-115">An array of length zero is trivially a permutation.</span></span>