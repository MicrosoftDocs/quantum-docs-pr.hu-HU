---
uid: Microsoft.Quantum.Arrays.Chunks
title: Adattömbök függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: fe10999d35ed05908fd59b9dad8b5c0c51233ae6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719465"
---
# <a name="chunks-function"></a><span data-ttu-id="dfb04-102">Adattömbök függvény</span><span class="sxs-lookup"><span data-stu-id="dfb04-102">Chunks function</span></span>

<span data-ttu-id="dfb04-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="dfb04-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="dfb04-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dfb04-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dfb04-105">Tömb felosztása több, egyenlő hosszúságú részre.</span><span class="sxs-lookup"><span data-stu-id="dfb04-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="dfb04-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="dfb04-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="dfb04-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dfb04-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dfb04-108">Az egyes adattömbök hossza.</span><span class="sxs-lookup"><span data-stu-id="dfb04-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="dfb04-109">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="dfb04-109">arr : 'T[]</span></span>

<span data-ttu-id="dfb04-110">A darabolni kívánt tömb.</span><span class="sxs-lookup"><span data-stu-id="dfb04-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="dfb04-111">Kimenet: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="dfb04-111">Output : 'T[][]</span></span>

<span data-ttu-id="dfb04-112">Az eredeti tömb minden egyes részletét tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="dfb04-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="dfb04-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="dfb04-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dfb04-114">Nem</span><span class="sxs-lookup"><span data-stu-id="dfb04-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="dfb04-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="dfb04-115">Remarks</span></span>

<span data-ttu-id="dfb04-116">Vegye figyelembe, hogy a kimenet utolsó eleme rövidebb lehet, mint `nElements` Ha a `Length(arr)` nem osztható meg `nElements` .</span><span class="sxs-lookup"><span data-stu-id="dfb04-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>