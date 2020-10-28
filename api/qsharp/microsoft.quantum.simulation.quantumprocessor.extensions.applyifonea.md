---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfOneA
title: ApplyIfOneA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfOneA
qsharp.summary: ''
ms.openlocfilehash: c18133403a545f7dc7b9f213a42ed09cd194f2d7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725391"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="72122-102">ApplyIfOneA művelet</span><span class="sxs-lookup"><span data-stu-id="72122-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="72122-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="72122-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="72122-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="72122-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfOneA<'T> (measurementResult : Result, (onResultOneOp : ('T => Unit is Adj), oneArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="72122-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="72122-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="72122-106">measurementResult: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="72122-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultoneop--t--unit-adj"></a><span data-ttu-id="72122-107">onResultOneOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="72122-107">onResultOneOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="onearg--t"></a><span data-ttu-id="72122-108">oneArg: nem</span><span class="sxs-lookup"><span data-stu-id="72122-108">oneArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="72122-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="72122-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="72122-110">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="72122-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="72122-111">Nem</span><span class="sxs-lookup"><span data-stu-id="72122-111">'T</span></span>

