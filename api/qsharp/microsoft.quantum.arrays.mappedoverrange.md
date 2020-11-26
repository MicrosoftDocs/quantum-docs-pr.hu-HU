---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: b1d73c2503e63ed09a3d6a56421760ca29eb0c3f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220688"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="91bf3-102">MappedOverRange függvény</span><span class="sxs-lookup"><span data-stu-id="91bf3-102">MappedOverRange function</span></span>

<span data-ttu-id="91bf3-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="91bf3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="91bf3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91bf3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91bf3-105">Egy tartomány és egy olyan függvény, amely egy egész számot fogad a bemenetként, egy új tömböt ad vissza, amely a függvényben lévő tartomány értékeiből származó képekből áll.</span><span class="sxs-lookup"><span data-stu-id="91bf3-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="91bf3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="91bf3-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="91bf3-107">Mapper: [int](xref:microsoft.quantum.lang-ref.int) -> 't</span><span class="sxs-lookup"><span data-stu-id="91bf3-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="91bf3-108">A-ből származó függvény, `Int` `'T` amely a tartomány értékeit térképezi fel.</span><span class="sxs-lookup"><span data-stu-id="91bf3-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="91bf3-109">tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="91bf3-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="91bf3-110">Egész számokból álló tartomány.</span><span class="sxs-lookup"><span data-stu-id="91bf3-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="91bf3-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="91bf3-111">Output : 'T[]</span></span>

<span data-ttu-id="91bf3-112">`'T[]`A függvény által leképezett elemek tömbje `mapper` .</span><span class="sxs-lookup"><span data-stu-id="91bf3-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="91bf3-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="91bf3-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="91bf3-114">Nem</span><span class="sxs-lookup"><span data-stu-id="91bf3-114">'T</span></span>

<span data-ttu-id="91bf3-115">A függvény eredményének típusa `mapper` .</span><span class="sxs-lookup"><span data-stu-id="91bf3-115">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="91bf3-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="91bf3-116">Remarks</span></span>

<span data-ttu-id="91bf3-117">A függvény általános típusokhoz van definiálva, például ha van egy függvény, amely `mapper: Int -> 'T` leképezi a tartomány értékeit, és létrehoz egy típusú tömböt `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="91bf3-117">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="91bf3-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="91bf3-118">See Also</span></span>

- [<span data-ttu-id="91bf3-119">Microsoft. Quantum. Arrays. leképezve</span><span class="sxs-lookup"><span data-stu-id="91bf3-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)