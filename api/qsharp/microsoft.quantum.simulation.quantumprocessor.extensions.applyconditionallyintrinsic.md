---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsic
title: ApplyConditionallyIntrinsic művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsic
qsharp.summary: ''
ms.openlocfilehash: 892e3140544d0b02c5fef085c89c3a4c8bafcde5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720172"
---
# <a name="applyconditionallyintrinsic-operation"></a><span data-ttu-id="99307-102">ApplyConditionallyIntrinsic művelet</span><span class="sxs-lookup"><span data-stu-id="99307-102">ApplyConditionallyIntrinsic operation</span></span>

<span data-ttu-id="99307-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="99307-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="99307-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="99307-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyConditionallyIntrinsic (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit), onNonEqualOp : (Unit => Unit)) : Unit
```


## <a name="input"></a><span data-ttu-id="99307-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="99307-105">Input</span></span>

### <a name="measurementresults--__invalidresult__"></a><span data-ttu-id="99307-106">measurementResults: __érvénytelen <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="99307-106">measurementResults : __invalid<Result>__ []</span></span>




### <a name="resultsvalues--__invalidresult__"></a><span data-ttu-id="99307-107">resultsValues: __érvénytelen <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="99307-107">resultsValues : __invalid<Result>__ []</span></span>




### <a name="onequalop--unit--unit"></a><span data-ttu-id="99307-108">onEqualOp: [egység](xref:microsoft.quantum.lang-ref.unit) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="99307-108">onEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onnonequalop--unit--unit"></a><span data-ttu-id="99307-109">onNonEqualOp: [egység](xref:microsoft.quantum.lang-ref.unit) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="99307-109">onNonEqualOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 





## <a name="output--unit"></a><span data-ttu-id="99307-110">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="99307-110">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>
