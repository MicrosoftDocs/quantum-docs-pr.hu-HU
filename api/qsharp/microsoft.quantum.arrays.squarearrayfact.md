---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: a154e5becba4dae762596a3fc1b268855520fa1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850968"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="4f7a5-102">SquareArrayFact függvény</span><span class="sxs-lookup"><span data-stu-id="4f7a5-102">SquareArrayFact function</span></span>

<span data-ttu-id="4f7a5-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4f7a5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4f7a5-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4f7a5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4f7a5-105">Azt a feltételt jelöli, hogy egy kétdimenziós tömb szögletes alakzattal rendelkezik</span><span class="sxs-lookup"><span data-stu-id="4f7a5-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="4f7a5-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="4f7a5-106">Description</span></span>

<span data-ttu-id="4f7a5-107">Ez a függvény azt állítja be, hogy egy tömb minden sora annyi elemet tartalmaz, mint a tömbben lévő sorok (elemek).</span><span class="sxs-lookup"><span data-stu-id="4f7a5-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="4f7a5-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4f7a5-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="4f7a5-109">tömb: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="4f7a5-109">array : 'T[][]</span></span>

<span data-ttu-id="4f7a5-110">Elemek kétdimenziós tömbje</span><span class="sxs-lookup"><span data-stu-id="4f7a5-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="4f7a5-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="4f7a5-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="4f7a5-112">Egy nyomtatandó üzenet, ha a tömb nem négyzet alakú tömb</span><span class="sxs-lookup"><span data-stu-id="4f7a5-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="4f7a5-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4f7a5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4f7a5-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="4f7a5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4f7a5-115">Nem</span><span class="sxs-lookup"><span data-stu-id="4f7a5-115">'T</span></span>

<span data-ttu-id="4f7a5-116">Az egyes elemeinek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="4f7a5-116">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="4f7a5-117">Példa</span><span class="sxs-lookup"><span data-stu-id="4f7a5-117">Example</span></span>

```qsharp
SquareArrayFact([[1, 2], [3, 4]], "Array is not a square");       // okay
SquareArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not a square"); // will fail
SquareArrayFact([[1, 2], [3, 4, 5]], "Array is not a square");    // will fail
```

## <a name="see-also"></a><span data-ttu-id="4f7a5-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="4f7a5-118">See Also</span></span>

- [<span data-ttu-id="4f7a5-119">Microsoft. Quantum. Arrays. RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="4f7a5-119">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)