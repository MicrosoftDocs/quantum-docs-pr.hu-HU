---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsicCA
title: ApplyIfElseIntrinsicCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsicCA
qsharp.summary: ''
ms.openlocfilehash: 40513e407d4f7a42dffde940cd4b3548d8738a4d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192655"
---
# <a name="applyifelseintrinsicca-operation"></a><span data-ttu-id="4df12-102">ApplyIfElseIntrinsicCA művelet</span><span class="sxs-lookup"><span data-stu-id="4df12-102">ApplyIfElseIntrinsicCA operation</span></span>

<span data-ttu-id="4df12-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="4df12-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="4df12-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4df12-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>




```qsharp
operation ApplyIfElseIntrinsicCA (measurementResult : Result, onResultZeroOp : (Unit => Unit is Ctl + Adj), onResultOneOp : (Unit => Unit is Ctl + Adj)) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4df12-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4df12-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="4df12-106">measurementResult: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="4df12-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit--is-adj--ctl"></a><span data-ttu-id="4df12-107">onResultZeroOp: [egység](xref:microsoft.quantum.lang-ref.unit) => [egysége](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="4df12-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>




### <a name="onresultoneop--unit--unit--is-adj--ctl"></a><span data-ttu-id="4df12-108">onResultOneOp: [egység](xref:microsoft.quantum.lang-ref.unit) => [egysége](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="4df12-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>





## <a name="output--unit"></a><span data-ttu-id="4df12-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4df12-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

