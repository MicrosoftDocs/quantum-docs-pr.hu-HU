---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: db20795719d11138cbdc5a38c0a19d0f247af059
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220773"
---
# <a name="lookupfunction-function"></a><span data-ttu-id="e6642-102">LookupFunction függvény</span><span class="sxs-lookup"><span data-stu-id="e6642-102">LookupFunction function</span></span>

<span data-ttu-id="e6642-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e6642-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e6642-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e6642-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e6642-105">A tömb adott értéke egy olyan függvényt ad vissza, amely a tömb elemeit adja vissza.</span><span class="sxs-lookup"><span data-stu-id="e6642-105">Given an array, returns a function which returns elements of that array.</span></span>

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a><span data-ttu-id="e6642-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e6642-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="e6642-107">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="e6642-107">array : 'T[]</span></span>

<span data-ttu-id="e6642-108">Az a tömb, amelyet keresési függvényként kell megjeleníteni.</span><span class="sxs-lookup"><span data-stu-id="e6642-108">The array to be represented as a lookup function.</span></span>



## <a name="output--int---t"></a><span data-ttu-id="e6642-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int) -> 't</span><span class="sxs-lookup"><span data-stu-id="e6642-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="e6642-110">Ilyen függvény `f` `f(idx) == f[idx]` .</span><span class="sxs-lookup"><span data-stu-id="e6642-110">A function `f` such that `f(idx) == f[idx]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e6642-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e6642-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e6642-112">Nem</span><span class="sxs-lookup"><span data-stu-id="e6642-112">'T</span></span>

<span data-ttu-id="e6642-113">A tömb azon elemeinek típusa, amelyek keresési függvényként jelennek meg.</span><span class="sxs-lookup"><span data-stu-id="e6642-113">The type of the elements of the array being represented as a lookup function.</span></span>

## <a name="remarks"></a><span data-ttu-id="e6642-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e6642-114">Remarks</span></span>

<span data-ttu-id="e6642-115">Ez a függvény elsősorban olyan függvényekkel és műveletekkel való együttműködésre hasznos, amelyek `Int -> 'T` argumentumként működnek.</span><span class="sxs-lookup"><span data-stu-id="e6642-115">This function is mainly useful for interoperating with functions and operations that take `Int -> 'T` functions as their arguments.</span></span> <span data-ttu-id="e6642-116">Ez gyakran előfordul, például a Generator reprezentációs könyvtárban, ahol a függvények használatával elkerülhető, hogy a teljes tömb ne legyen rögzítve a memóriában.</span><span class="sxs-lookup"><span data-stu-id="e6642-116">This is common, for instance, in the generator representation library, where functions are used to avoid the need to record an entire array in memory.</span></span>