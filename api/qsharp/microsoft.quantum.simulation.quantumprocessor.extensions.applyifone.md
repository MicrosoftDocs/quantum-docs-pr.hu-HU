---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOne
title: ApplyIfOne művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOne
qsharp.summary: ''
ms.openlocfilehash: f8f4f3b05d3986d94e6f1be380d6c83151d87f17
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230667"
---
# <a name="applyifone-operation"></a><span data-ttu-id="e5032-102">ApplyIfOne művelet</span><span class="sxs-lookup"><span data-stu-id="e5032-102">ApplyIfOne operation</span></span>

<span data-ttu-id="e5032-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="e5032-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="e5032-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e5032-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOne<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="e5032-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e5032-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="e5032-106">measurementResult: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="e5032-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit"></a><span data-ttu-id="e5032-107">onResultOneOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e5032-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--t"></a><span data-ttu-id="e5032-108">oneArg: nem</span><span class="sxs-lookup"><span data-stu-id="e5032-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="e5032-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e5032-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e5032-110">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e5032-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e5032-111">Nem</span><span class="sxs-lookup"><span data-stu-id="e5032-111">'T</span></span>

