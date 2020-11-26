---
uid: Microsoft.Quantum.Arrays.Unique
title: Egyedi függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: 7964d5d41eb68cb05f9414164d69496c1f76eb08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220008"
---
# <a name="unique-function"></a><span data-ttu-id="37481-102">Egyedi függvény</span><span class="sxs-lookup"><span data-stu-id="37481-102">Unique function</span></span>

<span data-ttu-id="37481-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="37481-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="37481-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="37481-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="37481-105">Egy olyan új tömböt ad vissza, amely nem tartalmaz egyenlő szomszédos elemeket.</span><span class="sxs-lookup"><span data-stu-id="37481-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="37481-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="37481-106">Description</span></span>

<span data-ttu-id="37481-107">A függvény az elemek egy tömbjét és egy olyan függvényt ad vissza, amely az elemek relatív sorrendjét tárolja, de az összes szomszédos elem, amely egyenlő, csak egyetlen elemre van szűrve.</span><span class="sxs-lookup"><span data-stu-id="37481-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="37481-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="37481-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="37481-109">egyenlő: (nem, 'T) – > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="37481-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="37481-110">Olyan függvény, amely összehasonlítja a két olyan elemet, amely az `a` `b` IF értékkel egyenlőnek tekintendő `equal(a, b)` `true` .</span><span class="sxs-lookup"><span data-stu-id="37481-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="37481-111">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="37481-111">array : 'T[]</span></span>

<span data-ttu-id="37481-112">Az egyedi elemek szűrésére szolgáló tömb.</span><span class="sxs-lookup"><span data-stu-id="37481-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="37481-113">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="37481-113">Output : 'T[]</span></span>

<span data-ttu-id="37481-114">Tömb, amely nem egyenlő szomszédos elemekből áll.</span><span class="sxs-lookup"><span data-stu-id="37481-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="37481-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="37481-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="37481-116">Nem</span><span class="sxs-lookup"><span data-stu-id="37481-116">'T</span></span>

<span data-ttu-id="37481-117">Az egyes elemeinek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="37481-117">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="37481-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="37481-118">Remarks</span></span>

<span data-ttu-id="37481-119">Ha több olyan elem van, amely egyenlő, de nem egymás mellett van, akkor a kimeneti tömbben több esemény is szerepel.</span><span class="sxs-lookup"><span data-stu-id="37481-119">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="37481-120">Ezt a függvényt együtt használva `Sorted` egy teljes egyedi elemmel rendelkező tömböt kaphat.</span><span class="sxs-lookup"><span data-stu-id="37481-120">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>