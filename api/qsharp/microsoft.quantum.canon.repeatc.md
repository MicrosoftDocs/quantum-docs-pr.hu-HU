---
uid: Microsoft.Quantum.Canon.RepeatC
title: RepeatC művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatC
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: efb820411be63352fc09ada2441a9140dd5575f9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840243"
---
# <a name="repeatc-operation"></a><span data-ttu-id="8d387-102">RepeatC művelet</span><span class="sxs-lookup"><span data-stu-id="8d387-102">RepeatC operation</span></span>

<span data-ttu-id="8d387-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8d387-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8d387-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8d387-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8d387-105">Adott számú alkalommal ismétli meg a műveletet.</span><span class="sxs-lookup"><span data-stu-id="8d387-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatC<'TInput> (op : ('TInput => Unit is Ctl), nTimes : Int, input : 'TInput) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="8d387-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8d387-106">Input</span></span>

### <a name="op--tinput--unit--is-ctl"></a><span data-ttu-id="8d387-107">op: ' TInput => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="8d387-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="8d387-108">A művelet, amelyet többször kell meghívni.</span><span class="sxs-lookup"><span data-stu-id="8d387-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="8d387-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8d387-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8d387-110">A hívni kívánt idő száma `op` .</span><span class="sxs-lookup"><span data-stu-id="8d387-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="8d387-111">bemenet: ' TInput</span><span class="sxs-lookup"><span data-stu-id="8d387-111">input : 'TInput</span></span>

<span data-ttu-id="8d387-112">Az átadandó bemenet `op` .</span><span class="sxs-lookup"><span data-stu-id="8d387-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8d387-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8d387-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8d387-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="8d387-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="8d387-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="8d387-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="8d387-116">Példa</span><span class="sxs-lookup"><span data-stu-id="8d387-116">Example</span></span>

<span data-ttu-id="8d387-117">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="8d387-117">The following are equivalent:</span></span>

```qsharp
RepeatC(U, 17, target);
(BoundC(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="8d387-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="8d387-118">See Also</span></span>

- [<span data-ttu-id="8d387-119">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="8d387-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="8d387-120">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="8d387-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="8d387-121">Microsoft. Quantum. Canon. Repeata</span><span class="sxs-lookup"><span data-stu-id="8d387-121">Microsoft.Quantum.Canon.RepeatA</span></span>](xref:Microsoft.Quantum.Canon.RepeatA)
- [<span data-ttu-id="8d387-122">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="8d387-122">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)