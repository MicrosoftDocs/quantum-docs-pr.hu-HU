---
uid: Microsoft.Quantum.Canon.RepeatCA
title: RepeatCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatCA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: af93220562d6be27b2f41e770bd953e5e808fcbf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852213"
---
# <a name="repeatca-operation"></a><span data-ttu-id="11b1f-102">RepeatCA művelet</span><span class="sxs-lookup"><span data-stu-id="11b1f-102">RepeatCA operation</span></span>

<span data-ttu-id="11b1f-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="11b1f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="11b1f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="11b1f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="11b1f-105">Adott számú alkalommal ismétli meg a műveletet.</span><span class="sxs-lookup"><span data-stu-id="11b1f-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatCA<'TInput> (op : ('TInput => Unit is Adj + Ctl), nTimes : Int, input : 'TInput) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="11b1f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="11b1f-106">Input</span></span>

### <a name="op--tinput--unit--is-adj--ctl"></a><span data-ttu-id="11b1f-107">op: ' TInput => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="11b1f-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="11b1f-108">A művelet, amelyet többször kell meghívni.</span><span class="sxs-lookup"><span data-stu-id="11b1f-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="11b1f-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="11b1f-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="11b1f-110">A hívni kívánt idő száma `op` .</span><span class="sxs-lookup"><span data-stu-id="11b1f-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="11b1f-111">bemenet: ' TInput</span><span class="sxs-lookup"><span data-stu-id="11b1f-111">input : 'TInput</span></span>

<span data-ttu-id="11b1f-112">Az átadandó bemenet `op` .</span><span class="sxs-lookup"><span data-stu-id="11b1f-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="11b1f-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="11b1f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="11b1f-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="11b1f-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="11b1f-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="11b1f-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="11b1f-116">Példa</span><span class="sxs-lookup"><span data-stu-id="11b1f-116">Example</span></span>

<span data-ttu-id="11b1f-117">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="11b1f-117">The following are equivalent:</span></span>

```qsharp
RepeatCA(U, 17, target);
(BoundCA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="11b1f-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="11b1f-118">See Also</span></span>

- [<span data-ttu-id="11b1f-119">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="11b1f-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="11b1f-120">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="11b1f-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="11b1f-121">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="11b1f-121">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="11b1f-122">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="11b1f-122">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)