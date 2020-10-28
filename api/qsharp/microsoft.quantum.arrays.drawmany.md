---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 601fe603a869dcf977c1ceade5819ee64f634d53
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719369"
---
# <a name="drawmany-operation"></a><span data-ttu-id="26e3d-102">DrawMany művelet</span><span class="sxs-lookup"><span data-stu-id="26e3d-102">DrawMany operation</span></span>

<span data-ttu-id="26e3d-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="26e3d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="26e3d-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="26e3d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="26e3d-105">Megismétli a műveletet egy adott számú minta esetében, és a kimenetét egy tömbben gyűjti össze.</span><span class="sxs-lookup"><span data-stu-id="26e3d-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="26e3d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="26e3d-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="26e3d-107">op: ' TInput => ' TOutput</span><span class="sxs-lookup"><span data-stu-id="26e3d-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="26e3d-108">A művelet, amelyet többször kell meghívni.</span><span class="sxs-lookup"><span data-stu-id="26e3d-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="26e3d-109">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="26e3d-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="26e3d-110">A gyűjtésre hívott minták száma `op` .</span><span class="sxs-lookup"><span data-stu-id="26e3d-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="26e3d-111">bemenet: ' TInput</span><span class="sxs-lookup"><span data-stu-id="26e3d-111">input : 'TInput</span></span>

<span data-ttu-id="26e3d-112">Az átadandó bemenet `op` .</span><span class="sxs-lookup"><span data-stu-id="26e3d-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="26e3d-113">Kimenet: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="26e3d-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="26e3d-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="26e3d-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="26e3d-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="26e3d-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="26e3d-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="26e3d-116">'TOutput</span></span>



## <a name="see-also"></a><span data-ttu-id="26e3d-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="26e3d-117">See Also</span></span>

- [<span data-ttu-id="26e3d-118">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="26e3d-118">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)