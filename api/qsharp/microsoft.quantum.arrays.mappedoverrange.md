---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: e527a3ca1fd7571836f4f79bb453581f53d1db2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719044"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="11345-102">MappedOverRange függvény</span><span class="sxs-lookup"><span data-stu-id="11345-102">MappedOverRange function</span></span>

<span data-ttu-id="11345-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="11345-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="11345-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="11345-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="11345-105">Egy tartomány és egy olyan függvény, amely egy egész számot fogad a bemenetként, egy új tömböt ad vissza, amely a függvényben lévő tartomány értékeiből származó képekből áll.</span><span class="sxs-lookup"><span data-stu-id="11345-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="11345-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="11345-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="11345-107">Mapper: [int](xref:microsoft.quantum.lang-ref.int) -> 't</span><span class="sxs-lookup"><span data-stu-id="11345-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="11345-108">A-ből származó függvény, `Int` `'T` amely a tartomány értékeit térképezi fel.</span><span class="sxs-lookup"><span data-stu-id="11345-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="11345-109">tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="11345-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="11345-110">Egész számokból álló tartomány.</span><span class="sxs-lookup"><span data-stu-id="11345-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="11345-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="11345-111">Output : 'T[]</span></span>

<span data-ttu-id="11345-112">`'T[]`A függvény által leképezett elemek tömbje `mapper` .</span><span class="sxs-lookup"><span data-stu-id="11345-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="11345-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="11345-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="11345-114">Nem</span><span class="sxs-lookup"><span data-stu-id="11345-114">'T</span></span>

<span data-ttu-id="11345-115">A függvény eredményének típusa `mapper` .</span><span class="sxs-lookup"><span data-stu-id="11345-115">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="11345-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="11345-116">Remarks</span></span>

<span data-ttu-id="11345-117">A függvény általános típusokhoz van definiálva, például ha van egy függvény, amely `mapper: Int -> 'T` leképezi a tartomány értékeit, és létrehoz egy típusú tömböt `'T[]` .</span><span class="sxs-lookup"><span data-stu-id="11345-117">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="11345-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="11345-118">See Also</span></span>

- [<span data-ttu-id="11345-119">Microsoft. Quantum. Arrays. leképezve</span><span class="sxs-lookup"><span data-stu-id="11345-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)