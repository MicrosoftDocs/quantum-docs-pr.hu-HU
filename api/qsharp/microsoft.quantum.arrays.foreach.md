---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: b362d28e77c8dea2b3daeed4a4d605e1dd42e487
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221147"
---
# <a name="foreach-operation"></a><span data-ttu-id="46252-102">ForEach művelet</span><span class="sxs-lookup"><span data-stu-id="46252-102">ForEach operation</span></span>

<span data-ttu-id="46252-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="46252-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="46252-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="46252-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="46252-105">Egy tömb és egy olyan művelet, amely a tömb elemeihez van meghatározva, egy új tömböt ad vissza, amely a művelet alatt található eredeti tömb képéből áll.</span><span class="sxs-lookup"><span data-stu-id="46252-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="46252-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="46252-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="46252-107">művelet: nem => ' U</span><span class="sxs-lookup"><span data-stu-id="46252-107">action : 'T => 'U</span></span> 

<span data-ttu-id="46252-108">Az `'T` `'U` összes elemre alkalmazott művelet.</span><span class="sxs-lookup"><span data-stu-id="46252-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="46252-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="46252-109">array : 'T[]</span></span>

<span data-ttu-id="46252-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="46252-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="46252-111">Kimenet: ' U []</span><span class="sxs-lookup"><span data-stu-id="46252-111">Output : 'U[]</span></span>

<span data-ttu-id="46252-112">`'U[]`A művelet által leképezett elemek tömbje `action` .</span><span class="sxs-lookup"><span data-stu-id="46252-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="46252-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="46252-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="46252-114">Nem</span><span class="sxs-lookup"><span data-stu-id="46252-114">'T</span></span>

<span data-ttu-id="46252-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="46252-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="46252-116">' U</span><span class="sxs-lookup"><span data-stu-id="46252-116">'U</span></span>

<span data-ttu-id="46252-117">A művelet eredményének típusa `action` .</span><span class="sxs-lookup"><span data-stu-id="46252-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="46252-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="46252-118">Remarks</span></span>

<span data-ttu-id="46252-119">A művelet általános típusokhoz van definiálva, azaz a tömb `'T[]` `action : 'T -> 'U` elemeinek leképezhetők, illetve egy új típusú tömb létrehozásához `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="46252-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>