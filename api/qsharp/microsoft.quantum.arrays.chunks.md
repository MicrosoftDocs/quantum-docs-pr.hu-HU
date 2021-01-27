---
uid: Microsoft.Quantum.Arrays.Chunks
title: Adattömbök függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Chunks
qsharp.summary: Splits an array into multiple parts of equal length.
ms.openlocfilehash: 977594839a7d2fe09de8138d32a4a50e8a752390
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842873"
---
# <a name="chunks-function"></a><span data-ttu-id="b2c06-102">Adattömbök függvény</span><span class="sxs-lookup"><span data-stu-id="b2c06-102">Chunks function</span></span>

<span data-ttu-id="b2c06-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b2c06-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b2c06-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b2c06-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b2c06-105">Tömb felosztása több, egyenlő hosszúságú részre.</span><span class="sxs-lookup"><span data-stu-id="b2c06-105">Splits an array into multiple parts of equal length.</span></span>

```qsharp
function Chunks<'T> (nElements : Int, arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="b2c06-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b2c06-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="b2c06-107">nElements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b2c06-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b2c06-108">Az egyes adattömbök hossza.</span><span class="sxs-lookup"><span data-stu-id="b2c06-108">The length of each chunk.</span></span>


### <a name="arr--t"></a><span data-ttu-id="b2c06-109">ARR: 'T []</span><span class="sxs-lookup"><span data-stu-id="b2c06-109">arr : 'T[]</span></span>

<span data-ttu-id="b2c06-110">A darabolni kívánt tömb.</span><span class="sxs-lookup"><span data-stu-id="b2c06-110">The array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="b2c06-111">Kimenet: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="b2c06-111">Output : 'T[][]</span></span>

<span data-ttu-id="b2c06-112">Az eredeti tömb minden egyes részletét tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="b2c06-112">A array containing each chunk of the original array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b2c06-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="b2c06-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b2c06-114">Nem</span><span class="sxs-lookup"><span data-stu-id="b2c06-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="b2c06-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b2c06-115">Remarks</span></span>

<span data-ttu-id="b2c06-116">Vegye figyelembe, hogy a kimenet utolsó eleme rövidebb lehet, mint `nElements` Ha a `Length(arr)` nem osztható meg `nElements` .</span><span class="sxs-lookup"><span data-stu-id="b2c06-116">Note that the last element of the output may be shorter than `nElements` if `Length(arr)` is not divisible by `nElements`.</span></span>