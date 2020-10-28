---
uid: Microsoft.Quantum.Arrays.Sorted
title: Rendezett függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: 14ac5325b81aec4ba0bf94a83cf00e086a075a7c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718888"
---
# <a name="sorted-function"></a><span data-ttu-id="a48b1-102">Rendezett függvény</span><span class="sxs-lookup"><span data-stu-id="a48b1-102">Sorted function</span></span>

<span data-ttu-id="a48b1-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a48b1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a48b1-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a48b1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a48b1-105">Egy tömb esetében a tömb azon elemeit adja vissza, amelyek egy adott összehasonlító függvény szerint vannak rendezve.</span><span class="sxs-lookup"><span data-stu-id="a48b1-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="a48b1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a48b1-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="a48b1-107">összehasonlítás: (nem, nem) – > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a48b1-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a48b1-108">Olyan függvény, amely összehasonlítja a két olyan elemet, amely az IF értéknél `a` kisebb vagy azzal egyenlő `b` `comparison(a, b)` `true` .</span><span class="sxs-lookup"><span data-stu-id="a48b1-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="a48b1-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="a48b1-109">array : 'T[]</span></span>

<span data-ttu-id="a48b1-110">A rendezendő tömb.</span><span class="sxs-lookup"><span data-stu-id="a48b1-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="a48b1-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="a48b1-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a48b1-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="a48b1-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a48b1-113">Nem</span><span class="sxs-lookup"><span data-stu-id="a48b1-113">'T</span></span>

<span data-ttu-id="a48b1-114">Az egyes elemeinek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="a48b1-114">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a48b1-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="a48b1-115">Remarks</span></span>

<span data-ttu-id="a48b1-116">`comparison`Feltételezzük, hogy a függvény tranzitív, például ha a `comparison(a, b)` és a `comparison(b, c)` , akkor `comparison(a, c)` feltételezzük.</span><span class="sxs-lookup"><span data-stu-id="a48b1-116">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="a48b1-117">Ha ez a tulajdonság nem áll fenn, akkor előfordulhat, hogy a függvény kimenete helytelen.</span><span class="sxs-lookup"><span data-stu-id="a48b1-117">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="a48b1-118">Mivel ez egy függvény, az eredmények teljesen determinstic, még akkor is, ha két elem egyenlőnek számít, `comparison` azaz, hogy mikor `comparison(a, b)` és `comparison(b, a)` mindkettőben `true` .</span><span class="sxs-lookup"><span data-stu-id="a48b1-118">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="a48b1-119">Különösen a függvény által végrehajtott rendezés garantáltan stabilnak minősül, így ha két elem van `a` `b` , és a sorrendben történik `array` , és a értéke a következő `comparison` , akkor `a` a kimenet előtt is megjelenik `b` .</span><span class="sxs-lookup"><span data-stu-id="a48b1-119">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="a48b1-120">Például:</span><span class="sxs-lookup"><span data-stu-id="a48b1-120">For example:</span></span>

```Q#
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```