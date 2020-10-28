---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: ab6ac6eb913095f31ba166ac27f034f2e2875acf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719201"
---
# <a name="foreach-operation"></a><span data-ttu-id="140b1-102">ForEach művelet</span><span class="sxs-lookup"><span data-stu-id="140b1-102">ForEach operation</span></span>

<span data-ttu-id="140b1-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="140b1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="140b1-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="140b1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="140b1-105">Egy tömb és egy olyan művelet, amely a tömb elemeihez van meghatározva, egy új tömböt ad vissza, amely a művelet alatt található eredeti tömb képéből áll.</span><span class="sxs-lookup"><span data-stu-id="140b1-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="140b1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="140b1-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="140b1-107">művelet: nem => ' U</span><span class="sxs-lookup"><span data-stu-id="140b1-107">action : 'T => 'U</span></span> 

<span data-ttu-id="140b1-108">Az `'T` `'U` összes elemre alkalmazott művelet.</span><span class="sxs-lookup"><span data-stu-id="140b1-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="140b1-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="140b1-109">array : 'T[]</span></span>

<span data-ttu-id="140b1-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="140b1-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="140b1-111">Kimenet: ' U []</span><span class="sxs-lookup"><span data-stu-id="140b1-111">Output : 'U[]</span></span>

<span data-ttu-id="140b1-112">`'U[]`A művelet által leképezett elemek tömbje `action` .</span><span class="sxs-lookup"><span data-stu-id="140b1-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="140b1-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="140b1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="140b1-114">Nem</span><span class="sxs-lookup"><span data-stu-id="140b1-114">'T</span></span>

<span data-ttu-id="140b1-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="140b1-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="140b1-116">' U</span><span class="sxs-lookup"><span data-stu-id="140b1-116">'U</span></span>

<span data-ttu-id="140b1-117">A művelet eredményének típusa `action` .</span><span class="sxs-lookup"><span data-stu-id="140b1-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="140b1-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="140b1-118">Remarks</span></span>

<span data-ttu-id="140b1-119">A művelet általános típusokhoz van definiálva, azaz a tömb `'T[]` `action : 'T -> 'U` elemeinek leképezhetők, illetve egy új típusú tömb létrehozásához `'U[]` .</span><span class="sxs-lookup"><span data-stu-id="140b1-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>