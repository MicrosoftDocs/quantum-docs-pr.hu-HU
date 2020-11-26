---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Particionált függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220501"
---
# <a name="partitioned-function"></a><span data-ttu-id="272da-102">Particionált függvény</span><span class="sxs-lookup"><span data-stu-id="272da-102">Partitioned function</span></span>

<span data-ttu-id="272da-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="272da-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="272da-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="272da-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="272da-105">Tömb felosztása több részre.</span><span class="sxs-lookup"><span data-stu-id="272da-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="272da-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="272da-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="272da-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="272da-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="272da-108">Elemek száma a tömb egyes részeiben</span><span class="sxs-lookup"><span data-stu-id="272da-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="272da-109">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="272da-109">arr : 'T[]</span></span>

<span data-ttu-id="272da-110">A feldarabolni kívánt bemeneti tömb.</span><span class="sxs-lookup"><span data-stu-id="272da-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="272da-111">Kimenet: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="272da-111">Output : 'T[][]</span></span>

<span data-ttu-id="272da-112">Több tömb, ahol az első tömb az első, `nElements[0]` `arr` a második tömb pedig a következő: `nElements[1]` `arr` Az utolsó tömb tartalmazni fogja az összes fennmaradó elemet.</span><span class="sxs-lookup"><span data-stu-id="272da-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="272da-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="272da-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="272da-114">Nem</span><span class="sxs-lookup"><span data-stu-id="272da-114">'T</span></span>

