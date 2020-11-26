---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 3185f2ec01a2b9d01cff82a0c4667f12483801a7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209995"
---
# <a name="drawmany-operation"></a><span data-ttu-id="1317b-102">DrawMany művelet</span><span class="sxs-lookup"><span data-stu-id="1317b-102">DrawMany operation</span></span>

<span data-ttu-id="1317b-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1317b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1317b-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1317b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1317b-105">Megismétli a műveletet egy adott számú minta esetében, és a kimenetét egy tömbben gyűjti össze.</span><span class="sxs-lookup"><span data-stu-id="1317b-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="1317b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1317b-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="1317b-107">op: ' TInput => ' TOutput</span><span class="sxs-lookup"><span data-stu-id="1317b-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="1317b-108">A művelet, amelyet többször kell meghívni.</span><span class="sxs-lookup"><span data-stu-id="1317b-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="1317b-109">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1317b-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1317b-110">A gyűjtésre hívott minták száma `op` .</span><span class="sxs-lookup"><span data-stu-id="1317b-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="1317b-111">bemenet: ' TInput</span><span class="sxs-lookup"><span data-stu-id="1317b-111">input : 'TInput</span></span>

<span data-ttu-id="1317b-112">Az átadandó bemenet `op` .</span><span class="sxs-lookup"><span data-stu-id="1317b-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="1317b-113">Kimenet: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="1317b-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1317b-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="1317b-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="1317b-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="1317b-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="1317b-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="1317b-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="1317b-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="1317b-117">See Also</span></span>

- [<span data-ttu-id="1317b-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="1317b-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)