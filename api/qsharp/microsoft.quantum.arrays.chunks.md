---
uid: Microsoft.Quantum.Arrays.Chunks
title: Adattömbök függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: b323fdab1b207c72a4f46d5ca4cb368ecf0df818
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221606"
---
# <a name="chunks-function"></a><span data-ttu-id="dfdd1-102">Adattömbök függvény</span><span class="sxs-lookup"><span data-stu-id="dfdd1-102">Chunks function</span></span>

<span data-ttu-id="dfdd1-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="dfdd1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="dfdd1-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dfdd1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dfdd1-105">Tömb felosztása több, egyenlő hosszúságú részre.</span><span class="sxs-lookup"><span data-stu-id="dfdd1-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="dfdd1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="dfdd1-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="dfdd1-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dfdd1-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dfdd1-108">Az egyes adattömbök hossza.</span><span class="sxs-lookup"><span data-stu-id="dfdd1-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="dfdd1-109">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="dfdd1-109">arr : 'T[]</span></span>

<span data-ttu-id="dfdd1-110">A darabolni kívánt tömb.</span><span class="sxs-lookup"><span data-stu-id="dfdd1-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="dfdd1-111">Kimenet: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="dfdd1-111">Output : 'T[][]</span></span>

<span data-ttu-id="dfdd1-112">Az eredeti tömb minden egyes részletét tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="dfdd1-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dfdd1-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="dfdd1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dfdd1-114">Nem</span><span class="sxs-lookup"><span data-stu-id="dfdd1-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="dfdd1-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="dfdd1-115">Remarks</span></span>

<span data-ttu-id="dfdd1-116">Vegye figyelembe, hogy a kimenet utolsó eleme rövidebb lehet, mint `nElements` Ha a `Length(arr)` nem osztható meg `nElements` .</span><span class="sxs-lookup"><span data-stu-id="dfdd1-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>