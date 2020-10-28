---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Particionált függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: e3395afeda206e255a58175b57245f91c588d978
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718973"
---
# <a name="partitioned-function"></a><span data-ttu-id="96c8d-102">Particionált függvény</span><span class="sxs-lookup"><span data-stu-id="96c8d-102">Partitioned function</span></span>

<span data-ttu-id="96c8d-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="96c8d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="96c8d-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="96c8d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="96c8d-105">Tömb felosztása több részre.</span><span class="sxs-lookup"><span data-stu-id="96c8d-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="96c8d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="96c8d-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="96c8d-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="96c8d-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="96c8d-108">Elemek száma a tömb egyes részeiben</span><span class="sxs-lookup"><span data-stu-id="96c8d-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="96c8d-109">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="96c8d-109">arr : 'T[]</span></span>

<span data-ttu-id="96c8d-110">A feldarabolni kívánt bemeneti tömb.</span><span class="sxs-lookup"><span data-stu-id="96c8d-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="96c8d-111">Kimenet: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="96c8d-111">Output : 'T[][]</span></span>

<span data-ttu-id="96c8d-112">Több tömb, ahol az első tömb az első, `nElements[0]` `arr` a második tömb pedig a következő: `nElements[1]` `arr` Az utolsó tömb tartalmazni fogja az összes fennmaradó elemet.</span><span class="sxs-lookup"><span data-stu-id="96c8d-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="96c8d-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="96c8d-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="96c8d-114">Nem</span><span class="sxs-lookup"><span data-stu-id="96c8d-114">'T</span></span>

