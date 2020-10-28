---
uid: Microsoft.Quantum.Canon.RepeatCA
title: RepeatCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: b68c3aa4298fffa76f7c43ac4c6d27cdf3b72fbf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715545"
---
# <a name="repeatca-operation"></a><span data-ttu-id="9b43c-102">RepeatCA művelet</span><span class="sxs-lookup"><span data-stu-id="9b43c-102">RepeatCA operation</span></span>

<span data-ttu-id="9b43c-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9b43c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9b43c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9b43c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9b43c-105">Adott számú alkalommal ismétli meg a műveletet.</span><span class="sxs-lookup"><span data-stu-id="9b43c-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit
```


## <a name="input"></a><span data-ttu-id="9b43c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9b43c-106">Input</span></span>

### <a name="op--tinput--unit-adj--ctl"></a><span data-ttu-id="9b43c-107">op: ' TInput => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="9b43c-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="9b43c-108">A művelet, amelyet többször kell meghívni.</span><span class="sxs-lookup"><span data-stu-id="9b43c-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="9b43c-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9b43c-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9b43c-110">A hívni kívánt idő száma `op` .</span><span class="sxs-lookup"><span data-stu-id="9b43c-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="9b43c-111">bemenet: ' TInput</span><span class="sxs-lookup"><span data-stu-id="9b43c-111">input : 'TInput</span></span>

<span data-ttu-id="9b43c-112">Az átadandó bemenet `op` .</span><span class="sxs-lookup"><span data-stu-id="9b43c-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9b43c-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b43c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9b43c-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="9b43c-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="9b43c-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="9b43c-115">'TInput</span></span>



## <a name="see-also"></a><span data-ttu-id="9b43c-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="9b43c-116">See Also</span></span>

- [<span data-ttu-id="9b43c-117">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="9b43c-117">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="9b43c-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="9b43c-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="9b43c-119">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="9b43c-119">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="9b43c-120">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="9b43c-120">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)