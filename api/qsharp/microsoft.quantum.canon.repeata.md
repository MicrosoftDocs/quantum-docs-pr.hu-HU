---
uid: Microsoft.Quantum.Canon.RepeatA
title: Ismétlési művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: RepeatA
qsharp.summary: Repeats an operation a given number of times.
ms.openlocfilehash: 9ae3123a64b2a886df3b7575b2840522f9b011ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852226"
---
# <a name="repeata-operation"></a><span data-ttu-id="97695-102">Ismétlési művelet</span><span class="sxs-lookup"><span data-stu-id="97695-102">RepeatA operation</span></span>

<span data-ttu-id="97695-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="97695-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="97695-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="97695-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="97695-105">Adott számú alkalommal ismétli meg a műveletet.</span><span class="sxs-lookup"><span data-stu-id="97695-105">Repeats an operation a given number of times.</span></span>

```qsharp
operation RepeatA<'TInput> (op : ('TInput => Unit is Adj), nTimes : Int, input : 'TInput) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="97695-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="97695-106">Input</span></span>

### <a name="op--tinput--unit--is-adj"></a><span data-ttu-id="97695-107">op: ' TInput => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="97695-107">op : 'TInput => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="97695-108">A művelet, amelyet többször kell meghívni.</span><span class="sxs-lookup"><span data-stu-id="97695-108">The operation to be called repeatedly.</span></span>


### <a name="ntimes--int"></a><span data-ttu-id="97695-109">nTimes: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97695-109">nTimes : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="97695-110">A hívni kívánt idő száma `op` .</span><span class="sxs-lookup"><span data-stu-id="97695-110">The number of times to call `op`.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="97695-111">bemenet: ' TInput</span><span class="sxs-lookup"><span data-stu-id="97695-111">input : 'TInput</span></span>

<span data-ttu-id="97695-112">Az átadandó bemenet `op` .</span><span class="sxs-lookup"><span data-stu-id="97695-112">The input to be passed to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="97695-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="97695-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="97695-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="97695-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="97695-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="97695-115">'TInput</span></span>



## <a name="example"></a><span data-ttu-id="97695-116">Példa</span><span class="sxs-lookup"><span data-stu-id="97695-116">Example</span></span>

<span data-ttu-id="97695-117">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="97695-117">The following are equivalent:</span></span>

```qsharp
RepeatA(U, 17, target);
(BoundA(ConstantArray(17, U)))(target);
```

## <a name="see-also"></a><span data-ttu-id="97695-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="97695-118">See Also</span></span>

- [<span data-ttu-id="97695-119">Microsoft. Quantum. Arrays. DrawMany</span><span class="sxs-lookup"><span data-stu-id="97695-119">Microsoft.Quantum.Arrays.DrawMany</span></span>](xref:Microsoft.Quantum.Arrays.DrawMany)
- [<span data-ttu-id="97695-120">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="97695-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)
- [<span data-ttu-id="97695-121">Microsoft. Quantum. Canon. RepeatC</span><span class="sxs-lookup"><span data-stu-id="97695-121">Microsoft.Quantum.Canon.RepeatC</span></span>](xref:Microsoft.Quantum.Canon.RepeatC)
- [<span data-ttu-id="97695-122">Microsoft. Quantum. Canon. RepeatCA</span><span class="sxs-lookup"><span data-stu-id="97695-122">Microsoft.Quantum.Canon.RepeatCA</span></span>](xref:Microsoft.Quantum.Canon.RepeatCA)