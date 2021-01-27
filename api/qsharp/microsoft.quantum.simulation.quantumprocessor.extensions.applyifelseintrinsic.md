---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsic
title: ApplyIfElseIntrinsic művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsic
qsharp.summary: ''
ms.openlocfilehash: 5956b4d017b05f9a61fb5dc3202c8ac2eef30606
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858754"
---
# <a name="applyifelseintrinsic-operation"></a><span data-ttu-id="d5f8c-102">ApplyIfElseIntrinsic művelet</span><span class="sxs-lookup"><span data-stu-id="d5f8c-102">ApplyIfElseIntrinsic operation</span></span>

<span data-ttu-id="d5f8c-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="d5f8c-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="d5f8c-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d5f8c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseIntrinsic (measurementResult : Result, onResultZeroOp : (Unit => Unit), onResultOneOp : (Unit => Unit)) : Unit
```


## <a name="input"></a><span data-ttu-id="d5f8c-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d5f8c-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="d5f8c-106">measurementResult: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="d5f8c-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit"></a><span data-ttu-id="d5f8c-107">onResultZeroOp: [egység](xref:microsoft.quantum.lang-ref.unit) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5f8c-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 




### <a name="onresultoneop--unit--unit"></a><span data-ttu-id="d5f8c-108">onResultOneOp: [egység](xref:microsoft.quantum.lang-ref.unit) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5f8c-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 





## <a name="output--unit"></a><span data-ttu-id="d5f8c-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5f8c-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

