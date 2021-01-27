---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: 8cf6b85da6e8fee7fc255a173753a6468d8134b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845489"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="3fc05-102">RectangularArrayFact függvény</span><span class="sxs-lookup"><span data-stu-id="3fc05-102">RectangularArrayFact function</span></span>

<span data-ttu-id="3fc05-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3fc05-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3fc05-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3fc05-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3fc05-105">Azt a feltételt jelöli, hogy egy kétdimenziós tömb téglalap alakú</span><span class="sxs-lookup"><span data-stu-id="3fc05-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="3fc05-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="3fc05-106">Description</span></span>

<span data-ttu-id="3fc05-107">Ez a függvény azt állítja be, hogy egy tömb minden sora azonos hosszúságú.</span><span class="sxs-lookup"><span data-stu-id="3fc05-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="3fc05-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3fc05-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="3fc05-109">tömb: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="3fc05-109">array : 'T[][]</span></span>

<span data-ttu-id="3fc05-110">Elemek kétdimenziós tömbje</span><span class="sxs-lookup"><span data-stu-id="3fc05-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="3fc05-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="3fc05-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="3fc05-112">Egy nyomtatandó üzenet, ha a tömb nem téglalap alakú tömb</span><span class="sxs-lookup"><span data-stu-id="3fc05-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="3fc05-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3fc05-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3fc05-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="3fc05-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3fc05-115">Nem</span><span class="sxs-lookup"><span data-stu-id="3fc05-115">'T</span></span>

<span data-ttu-id="3fc05-116">Az egyes elemeinek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="3fc05-116">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="3fc05-117">Példa</span><span class="sxs-lookup"><span data-stu-id="3fc05-117">Example</span></span>

```qsharp
RectangularArrayFact([[1, 2], [3, 4]], "Array is not rectangular");       // okay
RectangularArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not rectangular"); // okay
RectangularArrayFact([[1, 2], [3, 4, 5]], "Array is not rectangular");    // will fail
```

## <a name="see-also"></a><span data-ttu-id="3fc05-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="3fc05-118">See Also</span></span>

- [<span data-ttu-id="3fc05-119">Microsoft. Quantum. Arrays. SquareArrayFact</span><span class="sxs-lookup"><span data-stu-id="3fc05-119">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)