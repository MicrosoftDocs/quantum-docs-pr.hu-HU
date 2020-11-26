---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneA
title: ApplyIfOneA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneA
qsharp.summary: ''
ms.openlocfilehash: 93a72ee7174b0022b1fe30cd779dfc57e96d8033
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228270"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="4a90b-102">ApplyIfOneA művelet</span><span class="sxs-lookup"><span data-stu-id="4a90b-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="4a90b-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="4a90b-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="4a90b-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4a90b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOneA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Adj), oneArg : 'T)) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="4a90b-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4a90b-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="4a90b-106">measurementResult: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="4a90b-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit--is-adj"></a><span data-ttu-id="4a90b-107">onResultOneOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a90b-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>




### <a name="onearg--t"></a><span data-ttu-id="4a90b-108">oneArg: nem</span><span class="sxs-lookup"><span data-stu-id="4a90b-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="4a90b-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4a90b-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4a90b-110">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="4a90b-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4a90b-111">Nem</span><span class="sxs-lookup"><span data-stu-id="4a90b-111">'T</span></span>

