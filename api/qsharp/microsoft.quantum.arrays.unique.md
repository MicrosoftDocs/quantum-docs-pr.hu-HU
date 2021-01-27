---
uid: Microsoft.Quantum.Arrays.Unique
title: Egyedi függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: b3aa03d20195bdd8bb64783a9b68cafac29e68f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850913"
---
# <a name="unique-function"></a><span data-ttu-id="59047-102">Egyedi függvény</span><span class="sxs-lookup"><span data-stu-id="59047-102">Unique function</span></span>

<span data-ttu-id="59047-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="59047-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="59047-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="59047-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="59047-105">Egy olyan új tömböt ad vissza, amely nem tartalmaz egyenlő szomszédos elemeket.</span><span class="sxs-lookup"><span data-stu-id="59047-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="59047-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="59047-106">Description</span></span>

<span data-ttu-id="59047-107">A függvény az elemek egy tömbjét és egy olyan függvényt ad vissza, amely az elemek relatív sorrendjét tárolja, de az összes szomszédos elem, amely egyenlő, csak egyetlen elemre van szűrve.</span><span class="sxs-lookup"><span data-stu-id="59047-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="59047-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="59047-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="59047-109">egyenlő: (nem, 'T) – > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="59047-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="59047-110">Olyan függvény, amely összehasonlítja a két olyan elemet, amely az `a` `b` IF értékkel egyenlőnek tekintendő `equal(a, b)` `true` .</span><span class="sxs-lookup"><span data-stu-id="59047-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="59047-111">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="59047-111">array : 'T[]</span></span>

<span data-ttu-id="59047-112">Az egyedi elemek szűrésére szolgáló tömb.</span><span class="sxs-lookup"><span data-stu-id="59047-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="59047-113">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="59047-113">Output : 'T[]</span></span>

<span data-ttu-id="59047-114">Tömb, amely nem egyenlő szomszédos elemekből áll.</span><span class="sxs-lookup"><span data-stu-id="59047-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="59047-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="59047-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="59047-116">Nem</span><span class="sxs-lookup"><span data-stu-id="59047-116">'T</span></span>

<span data-ttu-id="59047-117">Az egyes elemeinek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="59047-117">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="59047-118">Példa</span><span class="sxs-lookup"><span data-stu-id="59047-118">Example</span></span>

```qsharp
let unique1 = Unique(EqualI, [1, 1, 3, 3, 2, 5, 5, 5, 7]);
// same as [1, 3, 2, 5, 7]
let unique2 = Unique(EqualI, [2, 2, 1, 1, 2, 2, 1, 1]);
// same as [2, 1, 2, 1];
let unique3 = Unique(EqualI, Sorted(LessThanOrEqualI, [2, 2, 1, 1, 2, 2, 1, 1]));
// same as [1, 2];
```

## <a name="remarks"></a><span data-ttu-id="59047-119">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="59047-119">Remarks</span></span>

<span data-ttu-id="59047-120">Ha több olyan elem van, amely egyenlő, de nem egymás mellett van, akkor a kimeneti tömbben több esemény is szerepel.</span><span class="sxs-lookup"><span data-stu-id="59047-120">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="59047-121">Ezt a függvényt együtt használva `Sorted` egy teljes egyedi elemmel rendelkező tömböt kaphat.</span><span class="sxs-lookup"><span data-stu-id="59047-121">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>