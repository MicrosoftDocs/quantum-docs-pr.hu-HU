---
uid: Microsoft.Quantum.Arrays.IsSorted
title: IsSorted függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: b2c5f11c0d92ddf9214de2d439c175319c569be0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220832"
---
# <a name="issorted-function"></a><span data-ttu-id="61f9b-102">IsSorted függvény</span><span class="sxs-lookup"><span data-stu-id="61f9b-102">IsSorted function</span></span>

<span data-ttu-id="61f9b-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="61f9b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="61f9b-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="61f9b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="61f9b-105">A tömb adott értéke azt adja vissza, hogy a tömb egy adott összehasonlító függvény által meghatározott módon van-e rendezve.</span><span class="sxs-lookup"><span data-stu-id="61f9b-105">Given an array, returns whether that array is sorted as defined by a given comparison function.</span></span>

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="61f9b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="61f9b-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="61f9b-107">összehasonlítás: (nem, nem) – > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="61f9b-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="61f9b-108">Olyan függvény, amely összehasonlítja a két olyan elemet, amely az IF értéknél `a` kisebb vagy azzal egyenlő `b` `comparison(a, b)` `true` .</span><span class="sxs-lookup"><span data-stu-id="61f9b-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="61f9b-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="61f9b-109">array : 'T[]</span></span>

<span data-ttu-id="61f9b-110">Az ellenőrizendő tömb.</span><span class="sxs-lookup"><span data-stu-id="61f9b-110">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="61f9b-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="61f9b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="61f9b-112">`true` Ha és csak akkor, ha az egyes elemekhez `a` és az `b` `array` adott sorrendben fordul elő, `comparison(a, b)` a a következő: `true` .</span><span class="sxs-lookup"><span data-stu-id="61f9b-112">`true` if and only if for each pair of elements `a` and `b` of `array` occuring in that order, `comparison(a, b)` is `true`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="61f9b-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="61f9b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="61f9b-114">Nem</span><span class="sxs-lookup"><span data-stu-id="61f9b-114">'T</span></span>

<span data-ttu-id="61f9b-115">Az egyes elemeinek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="61f9b-115">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="61f9b-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="61f9b-116">Remarks</span></span>

<span data-ttu-id="61f9b-117">`comparison`Feltételezzük, hogy a függvény tranzitív, például ha a `comparison(a, b)` és a `comparison(b, c)` , akkor `comparison(a, c)` feltételezzük.</span><span class="sxs-lookup"><span data-stu-id="61f9b-117">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="61f9b-118">Ha ez a tulajdonság nem áll fenn, akkor előfordulhat, hogy a függvény kimenete helytelen.</span><span class="sxs-lookup"><span data-stu-id="61f9b-118">If this property does not hold, then the output of this function may be incorrect.</span></span>