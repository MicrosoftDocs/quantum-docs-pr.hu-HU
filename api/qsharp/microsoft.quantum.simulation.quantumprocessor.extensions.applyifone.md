---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOne
title: ApplyIfOne művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOne
qsharp.summary: ''
ms.openlocfilehash: fd5ee65615e4910d60db83cb8ec4201cfff9035d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855593"
---
# <a name="applyifone-operation"></a><span data-ttu-id="5fe69-102">ApplyIfOne művelet</span><span class="sxs-lookup"><span data-stu-id="5fe69-102">ApplyIfOne operation</span></span>

<span data-ttu-id="5fe69-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="5fe69-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="5fe69-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5fe69-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfOne<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="5fe69-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5fe69-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="5fe69-106">measurementResult: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="5fe69-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit"></a><span data-ttu-id="5fe69-107">onResultOneOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5fe69-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onearg--t"></a><span data-ttu-id="5fe69-108">oneArg: nem</span><span class="sxs-lookup"><span data-stu-id="5fe69-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="5fe69-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5fe69-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="5fe69-110">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="5fe69-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5fe69-111">Nem</span><span class="sxs-lookup"><span data-stu-id="5fe69-111">'T</span></span>

