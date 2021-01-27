---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Particionált függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: 43d99a0e33a813e4af23a3890ace808e91c1049c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845542"
---
# <a name="partitioned-function"></a><span data-ttu-id="a9a1b-102">Particionált függvény</span><span class="sxs-lookup"><span data-stu-id="a9a1b-102">Partitioned function</span></span>

<span data-ttu-id="a9a1b-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a9a1b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a9a1b-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a9a1b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a9a1b-105">Tömb felosztása több részre.</span><span class="sxs-lookup"><span data-stu-id="a9a1b-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="a9a1b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a9a1b-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="a9a1b-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a9a1b-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="a9a1b-108">Elemek száma a tömb egyes részeiben</span><span class="sxs-lookup"><span data-stu-id="a9a1b-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="a9a1b-109">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="a9a1b-109">arr : 'T[]</span></span>

<span data-ttu-id="a9a1b-110">A feldarabolni kívánt bemeneti tömb.</span><span class="sxs-lookup"><span data-stu-id="a9a1b-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="a9a1b-111">Kimenet: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="a9a1b-111">Output : 'T[][]</span></span>

<span data-ttu-id="a9a1b-112">Több tömb, ahol az első tömb az első, `nElements[0]` `arr` a második tömb pedig a következő: `nElements[1]` `arr` Az utolsó tömb tartalmazni fogja az összes fennmaradó elemet.</span><span class="sxs-lookup"><span data-stu-id="a9a1b-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a9a1b-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="a9a1b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a9a1b-114">Nem</span><span class="sxs-lookup"><span data-stu-id="a9a1b-114">'T</span></span>



## <a name="example"></a><span data-ttu-id="a9a1b-115">Példa</span><span class="sxs-lookup"><span data-stu-id="a9a1b-115">Example</span></span>

```qsharp
// The following returns [[1, 5], [3], [7]];
let split = Partitioned([2,1], [1,5,3,7]);
```