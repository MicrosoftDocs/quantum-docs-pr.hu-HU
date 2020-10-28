---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: f7f0573db9098feebfd481624e11119c58fd9eed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718853"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="8f231-102">SquareArrayFact függvény</span><span class="sxs-lookup"><span data-stu-id="8f231-102">SquareArrayFact function</span></span>

<span data-ttu-id="8f231-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8f231-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8f231-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8f231-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8f231-105">Azt a feltételt jelöli, hogy egy kétdimenziós tömb szögletes alakzattal rendelkezik</span><span class="sxs-lookup"><span data-stu-id="8f231-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="8f231-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="8f231-106">Description</span></span>

<span data-ttu-id="8f231-107">Ez a függvény azt állítja be, hogy egy tömb minden sora annyi elemet tartalmaz, mint a tömbben lévő sorok (elemek).</span><span class="sxs-lookup"><span data-stu-id="8f231-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="8f231-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8f231-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="8f231-109">tömb: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="8f231-109">array : 'T[][]</span></span>

<span data-ttu-id="8f231-110">Elemek kétdimenziós tömbje</span><span class="sxs-lookup"><span data-stu-id="8f231-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="8f231-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="8f231-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="8f231-112">Egy nyomtatandó üzenet, ha a tömb nem négyzet alakú tömb</span><span class="sxs-lookup"><span data-stu-id="8f231-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="8f231-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8f231-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8f231-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="8f231-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8f231-115">Nem</span><span class="sxs-lookup"><span data-stu-id="8f231-115">'T</span></span>

<span data-ttu-id="8f231-116">Az egyes elemeinek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="8f231-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="8f231-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="8f231-117">See Also</span></span>

- [<span data-ttu-id="8f231-118">Microsoft. Quantum. Arrays. RectangularArrayFact</span><span class="sxs-lookup"><span data-stu-id="8f231-118">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)