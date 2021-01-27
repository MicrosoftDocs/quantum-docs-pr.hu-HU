---
uid: Microsoft.Quantum.Arrays.Fold
title: Fold függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848607"
---
# <a name="fold-function"></a><span data-ttu-id="0a485-102">Fold függvény</span><span class="sxs-lookup"><span data-stu-id="0a485-102">Fold function</span></span>

<span data-ttu-id="0a485-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0a485-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0a485-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0a485-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0a485-105">Megismétli a függvényt `f` egy tömbön keresztül `array` , visszatérve `f(f(f(initialState, array[0]), array[1]), ...)` .</span><span class="sxs-lookup"><span data-stu-id="0a485-105">Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.</span></span>

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a><span data-ttu-id="0a485-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0a485-106">Input</span></span>

### <a name="folder--statet---state"></a><span data-ttu-id="0a485-107">mappa: ("állapot, nem) – >" állapot</span><span class="sxs-lookup"><span data-stu-id="0a485-107">folder : ('State,'T) -> 'State</span></span>

<span data-ttu-id="0a485-108">A tömbben hajtogatható függvény.</span><span class="sxs-lookup"><span data-stu-id="0a485-108">A function to be folded over the array.</span></span>


### <a name="state--state"></a><span data-ttu-id="0a485-109">állapot: "állapot</span><span class="sxs-lookup"><span data-stu-id="0a485-109">state : 'State</span></span>

<span data-ttu-id="0a485-110">A mappa kezdeti állapota.</span><span class="sxs-lookup"><span data-stu-id="0a485-110">The initial state of the folder.</span></span>


### <a name="array--t"></a><span data-ttu-id="0a485-111">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="0a485-111">array : 'T[]</span></span>

<span data-ttu-id="0a485-112">Az áthajtogatható értékek tömbje.</span><span class="sxs-lookup"><span data-stu-id="0a485-112">An array of values to be folded over.</span></span>



## <a name="output--state"></a><span data-ttu-id="0a485-113">Kimenet: "State</span><span class="sxs-lookup"><span data-stu-id="0a485-113">Output : 'State</span></span>

<span data-ttu-id="0a485-114">A mappa által a összes elemének megismétlése után visszaadott végső állapot `array` .</span><span class="sxs-lookup"><span data-stu-id="0a485-114">The final state returned by the folder after iterating over all elements of `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0a485-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="0a485-115">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="0a485-116">"Állapot</span><span class="sxs-lookup"><span data-stu-id="0a485-116">'State</span></span>

<span data-ttu-id="0a485-117">A függvény által működtetett állapotok típusa `folder` , azaz az első argumentumként fogadja el az értéket, és visszaadja.</span><span class="sxs-lookup"><span data-stu-id="0a485-117">The type of states the `folder` function operates on, i.e., accepts as its first argument and returns.</span></span>
### <a name="t"></a><span data-ttu-id="0a485-118">Nem</span><span class="sxs-lookup"><span data-stu-id="0a485-118">'T</span></span>

<span data-ttu-id="0a485-119">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="0a485-119">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="0a485-120">Példa</span><span class="sxs-lookup"><span data-stu-id="0a485-120">Example</span></span>

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```