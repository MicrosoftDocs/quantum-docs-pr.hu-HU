---
uid: Microsoft.Quantum.Arrays.Fold
title: Fold függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: a42f9a832c18bd612c1ae416187f3f2513eed54d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221164"
---
# <a name="fold-function"></a><span data-ttu-id="51ca0-102">Fold függvény</span><span class="sxs-lookup"><span data-stu-id="51ca0-102">Fold function</span></span>

<span data-ttu-id="51ca0-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="51ca0-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="51ca0-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="51ca0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="51ca0-105">Megismétli a függvényt `f` egy tömbön keresztül `array` , visszatérve `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="51ca0-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="51ca0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="51ca0-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="51ca0-107">mappa: ("állapot, nem) – >" állapot</span><span class="sxs-lookup"><span data-stu-id="51ca0-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="51ca0-108">A tömbben hajtogatható függvény.</span><span class="sxs-lookup"><span data-stu-id="51ca0-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="51ca0-109">állapot: "állapot</span><span class="sxs-lookup"><span data-stu-id="51ca0-109">state : 'State</span></span>

<span data-ttu-id="51ca0-110">A mappa kezdeti állapota.</span><span class="sxs-lookup"><span data-stu-id="51ca0-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="51ca0-111">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="51ca0-111">array : 'T[]</span></span>

<span data-ttu-id="51ca0-112">Az áthajtogatható értékek tömbje.</span><span class="sxs-lookup"><span data-stu-id="51ca0-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="51ca0-113">Kimenet: "State</span><span class="sxs-lookup"><span data-stu-id="51ca0-113">Output : 'State</span></span>

<span data-ttu-id="51ca0-114">A mappa által a összes elemének megismétlése után visszaadott végső állapot `array` .</span><span class="sxs-lookup"><span data-stu-id="51ca0-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="51ca0-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="51ca0-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="51ca0-116">"Állapot</span><span class="sxs-lookup"><span data-stu-id="51ca0-116">'State</span></span>

<span data-ttu-id="51ca0-117">A függvény által működtetett állapotok típusa `folder` , azaz az első argumentumként fogadja el az értéket, és visszaadja.</span><span class="sxs-lookup"><span data-stu-id="51ca0-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="51ca0-118">Nem</span><span class="sxs-lookup"><span data-stu-id="51ca0-118">'T</span></span>

<span data-ttu-id="51ca0-119">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="51ca0-119">The type of `array` elements.</span></span>