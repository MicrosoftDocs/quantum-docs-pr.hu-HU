---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: ApplyConditionally művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: 24d52576d2fb3e83f294874be4b0d1cd6a80f188
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229069"
---
# <a name="applyconditionally-operation"></a><span data-ttu-id="7faf3-102">ApplyConditionally művelet</span><span class="sxs-lookup"><span data-stu-id="7faf3-102">ApplyConditionally operation</span></span>

<span data-ttu-id="7faf3-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="7faf3-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="7faf3-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="7faf3-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a><span data-ttu-id="7faf3-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7faf3-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="7faf3-106">measurementResults: __érvénytelen <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="7faf3-106">measurementResults : __invalid<Result>__[]</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="7faf3-107">resultsValues: __érvénytelen <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="7faf3-107">resultsValues : __invalid<Result>__[]</span></span>




### <a name="onequalop--t--unit"></a><span data-ttu-id="7faf3-108">onEqualOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7faf3-108">onEqualOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="equalarg--t"></a><span data-ttu-id="7faf3-109">equalArg: nem</span><span class="sxs-lookup"><span data-stu-id="7faf3-109">equalArg : 'T</span></span>




### <a name="onnonequalop--u--unit"></a><span data-ttu-id="7faf3-110">onNonEqualOp: ' U => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7faf3-110">onNonEqualOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="nonequalarg--u"></a><span data-ttu-id="7faf3-111">nonEqualArg: ' U</span><span class="sxs-lookup"><span data-stu-id="7faf3-111">nonEqualArg : 'U</span></span>





## <a name="output--unit"></a><span data-ttu-id="7faf3-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7faf3-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7faf3-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="7faf3-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7faf3-114">Nem</span><span class="sxs-lookup"><span data-stu-id="7faf3-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="7faf3-115">' U</span><span class="sxs-lookup"><span data-stu-id="7faf3-115">'U</span></span>

