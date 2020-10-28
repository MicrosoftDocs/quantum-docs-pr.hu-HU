---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: a09c2779c8f06d8f6b7b0902366f3cefbbca4525
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719393"
---
# <a name="cumulativefolded-function"></a><span data-ttu-id="6e71b-102">CumulativeFolded függvény</span><span class="sxs-lookup"><span data-stu-id="6e71b-102">CumulativeFolded function</span></span>

<span data-ttu-id="6e71b-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6e71b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6e71b-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6e71b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6e71b-105">A leképezett és a fold egyetlen függvénybe való egyesítése</span><span class="sxs-lookup"><span data-stu-id="6e71b-105">Combines Mapped and Fold into a single function</span></span>

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a><span data-ttu-id="6e71b-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="6e71b-106">Description</span></span>

<span data-ttu-id="6e71b-107">Ez a függvény `fn` a tömbön keresztül ismétli meg a függvényt, kezdve a kezdeti állapottól, `state` és az összes köztes értéket adja vissza, nem tartalmazza a kezdeti állapotot.</span><span class="sxs-lookup"><span data-stu-id="6e71b-107">This function iterates the `fn` function through the array, starting from an initial state `state` and returns all intermediate values, not including the inital state.</span></span>

## <a name="input"></a><span data-ttu-id="6e71b-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6e71b-108">Input</span></span>

### <a name="fn--statet---state"></a><span data-ttu-id="6e71b-109">FN: (' State, 'T)-> ' állapot</span><span class="sxs-lookup"><span data-stu-id="6e71b-109">fn : ('State,'T) -> 'State</span></span>

<span data-ttu-id="6e71b-110">A tömbben hajtogatható függvény</span><span class="sxs-lookup"><span data-stu-id="6e71b-110">A function to be folded over the array</span></span>


### <a name="state--state"></a><span data-ttu-id="6e71b-111">állapot: "állapot</span><span class="sxs-lookup"><span data-stu-id="6e71b-111">state : 'State</span></span>

<span data-ttu-id="6e71b-112">Az eldobni kívánt kezdeti állapot</span><span class="sxs-lookup"><span data-stu-id="6e71b-112">The initial state to be folded</span></span>


### <a name="array--t"></a><span data-ttu-id="6e71b-113">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="6e71b-113">array : 'T[]</span></span>

<span data-ttu-id="6e71b-114">Az áthajtogatható értékek tömbje</span><span class="sxs-lookup"><span data-stu-id="6e71b-114">An array of values to be folded over</span></span>



## <a name="output--state"></a><span data-ttu-id="6e71b-115">Kimenet: "State []</span><span class="sxs-lookup"><span data-stu-id="6e71b-115">Output : 'State[]</span></span>

<span data-ttu-id="6e71b-116">Az összes köztes állapot, beleértve a végső állapotot, de nem a kezdeti állapotot.</span><span class="sxs-lookup"><span data-stu-id="6e71b-116">All intermediate states, including the final state, but not the initial state.</span></span>
<span data-ttu-id="6e71b-117">A kimeneti tömb hossza megegyezik a hosszával `array` .</span><span class="sxs-lookup"><span data-stu-id="6e71b-117">The length of the output array is of the same length as `array`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6e71b-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="6e71b-118">Type Parameters</span></span>

### <a name="state"></a><span data-ttu-id="6e71b-119">"Állapot</span><span class="sxs-lookup"><span data-stu-id="6e71b-119">'State</span></span>

<span data-ttu-id="6e71b-120">A függvény által működtetett állapotok típusa `fn` , azaz az első bemenetként fogadja, és visszaadja.</span><span class="sxs-lookup"><span data-stu-id="6e71b-120">The type of states that the `fn` function operates on, i.e., accepts as its first input and returns.</span></span>
### <a name="t"></a><span data-ttu-id="6e71b-121">Nem</span><span class="sxs-lookup"><span data-stu-id="6e71b-121">'T</span></span>

<span data-ttu-id="6e71b-122">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="6e71b-122">The type of `array` elements.</span></span>