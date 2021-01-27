---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: 7093043e2a290e6132774b8fe154d3627a254f27
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845651"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="4b6b3-102">MappedOverRange függvény</span><span class="sxs-lookup"><span data-stu-id="4b6b3-102">MappedOverRange function</span></span>

<span data-ttu-id="4b6b3-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4b6b3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4b6b3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4b6b3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4b6b3-105">Egy tartomány és egy olyan függvény, amely egy egész számot fogad a bemenetként, egy új tömböt ad vissza, amely a függvényben lévő tartomány értékeiből származó képekből áll.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="4b6b3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4b6b3-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="4b6b3-107">Mapper: [int](xref:microsoft.quantum.lang-ref.int) -> 't</span><span class="sxs-lookup"><span data-stu-id="4b6b3-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="4b6b3-108">A-ből származó függvény, `Int` `'T` amely a tartomány értékeit térképezi fel.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="4b6b3-109">tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="4b6b3-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="4b6b3-110">Egész számokból álló tartomány.</span><span class="sxs-lookup"><span data-stu-id="4b6b3-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="4b6b3-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="4b6b3-111">Output : 'T[]</span></span>

<span data-ttu-id="4b6b3-112">`'T[]`A függvény által leképezett elemek tömbje `mapper` .</span><span class="sxs-lookup"><span data-stu-id="4b6b3-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4b6b3-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="4b6b3-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4b6b3-114">Nem</span><span class="sxs-lookup"><span data-stu-id="4b6b3-114">'T</span></span>

<span data-ttu-id="4b6b3-115">A függvény eredményének típusa `mapper` .</span><span class="sxs-lookup"><span data-stu-id="4b6b3-115">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="4b6b3-116">Példa</span><span class="sxs-lookup"><span data-stu-id="4b6b3-116">Example</span></span>

<span data-ttu-id="4b6b3-117">Ez a példa a páros számok egy tartományát adja hozzá 1-re:</span><span class="sxs-lookup"><span data-stu-id="4b6b3-117">This example adds 1 to a range of even numbers:</span></span>

```qsharp
let numbers = MappedOverRange(PlusI(1, _), 0..2..10);
// numbers = [1, 3, 5, 7, 9, 11]
```

## <a name="remarks"></a><span data-ttu-id="4b6b3-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="4b6b3-118">Remarks</span></span>

<span data-ttu-id="4b6b3-119">A függvény általános típusokhoz van definiálva, például ha van egy függvény, amely `mapper: Int -> 'T` leképezi a tartomány értékeit, és létrehoz egy típusú tömböt `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="4b6b3-119">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b6b3-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="4b6b3-120">See Also</span></span>

- [<span data-ttu-id="4b6b3-121">Microsoft. Quantum. Arrays. leképezve</span><span class="sxs-lookup"><span data-stu-id="4b6b3-121">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)