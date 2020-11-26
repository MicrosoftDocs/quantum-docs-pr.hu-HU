---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: b8ef7d52f7f815ca3e21ded1236e775a381646cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220416"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="cbe80-102">RectangularArrayFact függvény</span><span class="sxs-lookup"><span data-stu-id="cbe80-102">RectangularArrayFact function</span></span>

<span data-ttu-id="cbe80-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="cbe80-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="cbe80-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cbe80-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cbe80-105">Azt a feltételt jelöli, hogy egy kétdimenziós tömb téglalap alakú</span><span class="sxs-lookup"><span data-stu-id="cbe80-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="cbe80-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="cbe80-106">Description</span></span>

<span data-ttu-id="cbe80-107">Ez a függvény azt állítja be, hogy egy tömb minden sora azonos hosszúságú.</span><span class="sxs-lookup"><span data-stu-id="cbe80-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="cbe80-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="cbe80-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="cbe80-109">tömb: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="cbe80-109">array : 'T[][]</span></span>

<span data-ttu-id="cbe80-110">Elemek kétdimenziós tömbje</span><span class="sxs-lookup"><span data-stu-id="cbe80-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="cbe80-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="cbe80-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="cbe80-112">Egy nyomtatandó üzenet, ha a tömb nem téglalap alakú tömb</span><span class="sxs-lookup"><span data-stu-id="cbe80-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="cbe80-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cbe80-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cbe80-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="cbe80-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cbe80-115">Nem</span><span class="sxs-lookup"><span data-stu-id="cbe80-115">'T</span></span>

<span data-ttu-id="cbe80-116">Az egyes elemeinek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="cbe80-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="cbe80-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="cbe80-117">See Also</span></span>

- [<span data-ttu-id="cbe80-118">Microsoft. Quantum. Arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="cbe80-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)