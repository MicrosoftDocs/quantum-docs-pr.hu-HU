---
uid: Microsoft.Quantum.Arrays.IsSorted
title: IsSorted függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: 330c1f789585f64cf255bc74f8a9c1ccf81b009e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719104"
---
# <a name="issorted-function"></a><span data-ttu-id="46d06-102">IsSorted függvény</span><span class="sxs-lookup"><span data-stu-id="46d06-102">IsSorted function</span></span>

<span data-ttu-id="46d06-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="46d06-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="46d06-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="46d06-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="46d06-105">A tömb adott értéke azt adja vissza, hogy a tömb egy adott összehasonlító függvény által meghatározott módon van-e rendezve.</span><span class="sxs-lookup"><span data-stu-id="46d06-105">Given an array, returns whether that array is sorted as defined by a given comparison function.</span></span>

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="46d06-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="46d06-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="46d06-107">összehasonlítás: (nem, nem) – > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="46d06-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="46d06-108">Olyan függvény, amely összehasonlítja a két olyan elemet, amely az IF értéknél `a` kisebb vagy azzal egyenlő `b` `comparison(a, b)` `true` .</span><span class="sxs-lookup"><span data-stu-id="46d06-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="46d06-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="46d06-109">array : 'T[]</span></span>

<span data-ttu-id="46d06-110">Az ellenőrizendő tömb.</span><span class="sxs-lookup"><span data-stu-id="46d06-110">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="46d06-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="46d06-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="46d06-112">`true` Ha és csak akkor, ha az egyes elemekhez `a` és az `b` `array` adott sorrendben fordul elő, `comparison(a, b)` a a következő: `true` .</span><span class="sxs-lookup"><span data-stu-id="46d06-112">`true` if and only if for each pair of elements `a` and `b` of `array` occuring in that order, `comparison(a, b)` is `true`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="46d06-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="46d06-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="46d06-114">Nem</span><span class="sxs-lookup"><span data-stu-id="46d06-114">'T</span></span>

<span data-ttu-id="46d06-115">Az egyes elemeinek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="46d06-115">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="46d06-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="46d06-116">Remarks</span></span>

<span data-ttu-id="46d06-117">`comparison`Feltételezzük, hogy a függvény tranzitív, például ha a `comparison(a, b)` és a `comparison(b, c)` , akkor `comparison(a, c)` feltételezzük.</span><span class="sxs-lookup"><span data-stu-id="46d06-117">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="46d06-118">Ha ez a tulajdonság nem áll fenn, akkor előfordulhat, hogy a függvény kimenete helytelen.</span><span class="sxs-lookup"><span data-stu-id="46d06-118">If this property does not hold, then the output of this function may be incorrect.</span></span>