---
uid: Microsoft.Quantum.Canon.Repeat
title: Ismétlési művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Repeat
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: cd572e5e082df94d762a0869ad2c1923fb71fd3d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205592"
---
# <a name="repeat-operation"></a><span data-ttu-id="3012a-102">Ismétlési művelet</span><span class="sxs-lookup"><span data-stu-id="3012a-102">Repeat operation</span></span>

<span data-ttu-id="3012a-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3012a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3012a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3012a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3012a-105">Adott számú alkalommal ismétli meg a műveletet.</span><span class="sxs-lookup"><span data-stu-id="3012a-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation Repeat<'TInput> (op : ('TInput => Unit), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="3012a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3012a-106">Input</span></span>

### <a name="op--tinput--unit"></a><span data-ttu-id="3012a-107">op: ' TInput => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3012a-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="3012a-108">A művelet, amelyet többször kell meghívni.</span><span class="sxs-lookup"><span data-stu-id="3012a-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="3012a-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3012a-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3012a-110">A hívni kívánt idő száma `op` .</span><span class="sxs-lookup"><span data-stu-id="3012a-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="3012a-111">bemenet: ' TInput</span><span class="sxs-lookup"><span data-stu-id="3012a-111">input : 'TInput</span></span>

<span data-ttu-id="3012a-112">Az átadandó bemenet `op` .</span><span class="sxs-lookup"><span data-stu-id="3012a-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3012a-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3012a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3012a-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="3012a-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="3012a-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="3012a-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="3012a-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="3012a-116">See Also</span></span>

- [<span data-ttu-id="3012a-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="3012a-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="3012a-118">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="3012a-118">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="3012a-119">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="3012a-119">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="3012a-120">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="3012a-120">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)