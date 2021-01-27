---
uid: Microsoft.Quantum.Arrays.DrawMany
title: DrawMany művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846207"
---
# <a name="drawmany-operation"></a><span data-ttu-id="c96fb-102">DrawMany művelet</span><span class="sxs-lookup"><span data-stu-id="c96fb-102">DrawMany operation</span></span>

<span data-ttu-id="c96fb-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c96fb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c96fb-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c96fb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c96fb-105">Megismétli a műveletet egy adott számú minta esetében, és a kimenetét egy tömbben gyűjti össze.</span><span class="sxs-lookup"><span data-stu-id="c96fb-105">Repeats an operation for a given number of samples, collecting its outputs in an array.</span></span>

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="c96fb-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c96fb-106">Input</span></span>

### <a name="op--tinput--toutput"></a><span data-ttu-id="c96fb-107">op: ' TInput => ' TOutput</span><span class="sxs-lookup"><span data-stu-id="c96fb-107">op : 'TInput => 'TOutput</span></span> 

<span data-ttu-id="c96fb-108">A művelet, amelyet többször kell meghívni.</span><span class="sxs-lookup"><span data-stu-id="c96fb-108">The operation to be called repeatedly.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="c96fb-109">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c96fb-109">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c96fb-110">A gyűjtésre hívott minták száma `op` .</span><span class="sxs-lookup"><span data-stu-id="c96fb-110">The number of samples of calling `op` to collect.</span></span>


### <a name="input--tinput"></a><span data-ttu-id="c96fb-111">bemenet: ' TInput</span><span class="sxs-lookup"><span data-stu-id="c96fb-111">input : 'TInput</span></span>

<span data-ttu-id="c96fb-112">Az átadandó bemenet `op` .</span><span class="sxs-lookup"><span data-stu-id="c96fb-112">The input to be passed to `op`.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="c96fb-113">Kimenet: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="c96fb-113">Output : 'TOutput[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c96fb-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c96fb-114">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="c96fb-115">'TInput</span><span class="sxs-lookup"><span data-stu-id="c96fb-115">'TInput</span></span>


### <a name="toutput"></a><span data-ttu-id="c96fb-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="c96fb-116">'TOutput</span></span>



## <a name="example"></a><span data-ttu-id="c96fb-117">Példa</span><span class="sxs-lookup"><span data-stu-id="c96fb-117">Example</span></span>

<span data-ttu-id="c96fb-118">A következő minta egy egész számot adott meg egy olyan műveletből, amely egyszerre egyetlen bitet vesz fel.</span><span class="sxs-lookup"><span data-stu-id="c96fb-118">The following samples an integer, given an operation that samples a single bit at a time.</span></span>

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a><span data-ttu-id="c96fb-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="c96fb-119">See Also</span></span>

- [<span data-ttu-id="c96fb-120">Microsoft. Quantum. Canon. REPEAT</span><span class="sxs-lookup"><span data-stu-id="c96fb-120">Microsoft.Quantum.Canon.Repeat</span></span>](xref:Microsoft.Quantum.Canon.Repeat)