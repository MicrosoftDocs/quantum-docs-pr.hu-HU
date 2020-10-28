---
uid: Microsoft.Quantum.Canon._MultiplexOperationsFromGenerator
title: _MultiplexOperationsFromGenerator művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: _MultiplexOperationsFromGenerator
qsharp.summary: Implementation step of `MultiplexOperationsFromGenerator`.
ms.openlocfilehash: 17d8f3e9b800e26a00969418ca061e3ea1d97682
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718505"
---
# <a name="_multiplexoperationsfromgenerator-operation"></a><span data-ttu-id="87ed0-102">_MultiplexOperationsFromGenerator művelet</span><span class="sxs-lookup"><span data-stu-id="87ed0-102">_MultiplexOperationsFromGenerator operation</span></span>

<span data-ttu-id="87ed0-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="87ed0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="87ed0-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="87ed0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="87ed0-105">A megvalósításának lépése `MultiplexOperationsFromGenerator` .</span><span class="sxs-lookup"><span data-stu-id="87ed0-105">Implementation step of `MultiplexOperationsFromGenerator`.</span></span>

```qsharp
operation _MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, Int, (Int -> ('T => Unit is Adj + Ctl))), auxiliary : Qubit[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="87ed0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="87ed0-106">Input</span></span>

### <a name="unitarygenerator--intintint---t--unit-adj--ctl"></a><span data-ttu-id="87ed0-107">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 't => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL)</span><span class="sxs-lookup"><span data-stu-id="87ed0-107">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>




### <a name="auxiliary--qubit"></a><span data-ttu-id="87ed0-108">kiegészítő: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="87ed0-108">auxiliary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="index--littleendian"></a><span data-ttu-id="87ed0-109">index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="87ed0-109">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>




### <a name="target--t"></a><span data-ttu-id="87ed0-110">cél: nem</span><span class="sxs-lookup"><span data-stu-id="87ed0-110">target : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="87ed0-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="87ed0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="87ed0-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="87ed0-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="87ed0-113">Nem</span><span class="sxs-lookup"><span data-stu-id="87ed0-113">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="87ed0-114">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="87ed0-114">See Also</span></span>

- [<span data-ttu-id="87ed0-115">Microsoft. Quantum. Canon. MultiplexOperationsFromGenerator</span><span class="sxs-lookup"><span data-stu-id="87ed0-115">Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator</span></span>](xref:Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator)