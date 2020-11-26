---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: 3529718f0c903266d21fd593c11c0149dae0fa2c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220195"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="84c16-102">SquareArrayFact függvény</span><span class="sxs-lookup"><span data-stu-id="84c16-102">SquareArrayFact function</span></span>

<span data-ttu-id="84c16-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="84c16-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="84c16-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="84c16-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="84c16-105">Azt a feltételt jelöli, hogy egy kétdimenziós tömb szögletes alakzattal rendelkezik</span><span class="sxs-lookup"><span data-stu-id="84c16-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="84c16-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="84c16-106">Description</span></span>

<span data-ttu-id="84c16-107">Ez a függvény azt állítja be, hogy egy tömb minden sora annyi elemet tartalmaz, mint a tömbben lévő sorok (elemek).</span><span class="sxs-lookup"><span data-stu-id="84c16-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="84c16-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="84c16-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="84c16-109">tömb: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="84c16-109">array : 'T[][]</span></span>

<span data-ttu-id="84c16-110">Elemek kétdimenziós tömbje</span><span class="sxs-lookup"><span data-stu-id="84c16-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="84c16-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="84c16-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="84c16-112">Egy nyomtatandó üzenet, ha a tömb nem négyzet alakú tömb</span><span class="sxs-lookup"><span data-stu-id="84c16-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="84c16-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="84c16-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="84c16-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="84c16-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="84c16-115">Nem</span><span class="sxs-lookup"><span data-stu-id="84c16-115">'T</span></span>

<span data-ttu-id="84c16-116">Az egyes elemeinek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="84c16-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="84c16-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="84c16-117">See Also</span></span>

- [<span data-ttu-id="84c16-118">Microsoft. Quantum. Arrays. RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="84c16-118">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)