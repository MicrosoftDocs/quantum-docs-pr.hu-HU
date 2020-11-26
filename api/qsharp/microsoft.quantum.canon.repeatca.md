---
uid: Microsoft.Quantum.Canon.RepeatCA
title: RepeatCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 24606486b3d5703065a7c7f62d3bbc7e3d07615f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205405"
---
# <a name="repeatca-operation"></a><span data-ttu-id="a1560-102">RepeatCA művelet</span><span class="sxs-lookup"><span data-stu-id="a1560-102">RepeatCA operation</span></span>

<span data-ttu-id="a1560-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a1560-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a1560-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a1560-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a1560-105">Adott számú alkalommal ismétli meg a műveletet.</span><span class="sxs-lookup"><span data-stu-id="a1560-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a1560-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a1560-106">Input</span></span>

### <a name="op--tinput--unit--is-adj--ctl"></a><span data-ttu-id="a1560-107">op: ' TInput => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="a1560-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a1560-108">A művelet, amelyet többször kell meghívni.</span><span class="sxs-lookup"><span data-stu-id="a1560-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="a1560-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a1560-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a1560-110">A hívni kívánt idő száma `op` .</span><span class="sxs-lookup"><span data-stu-id="a1560-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="a1560-111">bemenet: ' TInput</span><span class="sxs-lookup"><span data-stu-id="a1560-111">input : 'TInput</span></span>

<span data-ttu-id="a1560-112">Az átadandó bemenet `op` .</span><span class="sxs-lookup"><span data-stu-id="a1560-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a1560-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a1560-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a1560-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="a1560-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="a1560-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="a1560-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="a1560-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="a1560-116">See Also</span></span>

- [<span data-ttu-id="a1560-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="a1560-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="a1560-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="a1560-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="a1560-119">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="a1560-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="a1560-120">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="a1560-120">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)