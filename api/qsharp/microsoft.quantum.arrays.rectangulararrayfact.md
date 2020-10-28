---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: f0d3f4d6bfa9e86f1c7a91792c09e16fe86433a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718924"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="e70bb-102">RectangularArrayFact függvény</span><span class="sxs-lookup"><span data-stu-id="e70bb-102">RectangularArrayFact function</span></span>

<span data-ttu-id="e70bb-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e70bb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e70bb-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e70bb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e70bb-105">Azt a feltételt jelöli, hogy egy kétdimenziós tömb téglalap alakú</span><span class="sxs-lookup"><span data-stu-id="e70bb-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="e70bb-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="e70bb-106">Description</span></span>

<span data-ttu-id="e70bb-107">Ez a függvény azt állítja be, hogy egy tömb minden sora azonos hosszúságú.</span><span class="sxs-lookup"><span data-stu-id="e70bb-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="e70bb-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e70bb-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="e70bb-109">tömb: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="e70bb-109">array : 'T[][]</span></span>

<span data-ttu-id="e70bb-110">Elemek kétdimenziós tömbje</span><span class="sxs-lookup"><span data-stu-id="e70bb-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="e70bb-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e70bb-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e70bb-112">Egy nyomtatandó üzenet, ha a tömb nem téglalap alakú tömb</span><span class="sxs-lookup"><span data-stu-id="e70bb-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="e70bb-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e70bb-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e70bb-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e70bb-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e70bb-115">Nem</span><span class="sxs-lookup"><span data-stu-id="e70bb-115">'T</span></span>

<span data-ttu-id="e70bb-116">Az egyes elemeinek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="e70bb-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e70bb-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e70bb-117">See Also</span></span>

- [<span data-ttu-id="e70bb-118">Microsoft. Quantum. Arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="e70bb-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)