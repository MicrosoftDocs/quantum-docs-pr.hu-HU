---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfElseIntrinsicA
title: ApplyIfElseIntrinsicA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfElseIntrinsicA
qsharp.summary: ''
ms.openlocfilehash: 68d9e02fd19df008f2d42b4f04b585a441b2408a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720124"
---
# <a name="applyifelseintrinsica-operation"></a><span data-ttu-id="c0ab9-102">ApplyIfElseIntrinsicA művelet</span><span class="sxs-lookup"><span data-stu-id="c0ab9-102">ApplyIfElseIntrinsicA operation</span></span>

<span data-ttu-id="c0ab9-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="c0ab9-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="c0ab9-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c0ab9-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfElseIntrinsicA (measurementResult : Result, onResultZeroOp : (Unit => Unit is Adj), onResultOneOp : (Unit => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="c0ab9-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c0ab9-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="c0ab9-106">measurementResult: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="c0ab9-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--unit--unit-adj"></a><span data-ttu-id="c0ab9-107">onResultZeroOp: [egység](xref:microsoft.quantum.lang-ref.unit) => [egysége](xref:microsoft.quantum.lang-ref.unit) – helyesbítés</span><span class="sxs-lookup"><span data-stu-id="c0ab9-107">onResultZeroOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="onresultoneop--unit--unit-adj"></a><span data-ttu-id="c0ab9-108">onResultOneOp: [egység](xref:microsoft.quantum.lang-ref.unit) => [egysége](xref:microsoft.quantum.lang-ref.unit) – helyesbítés</span><span class="sxs-lookup"><span data-stu-id="c0ab9-108">onResultOneOp : [Unit](xref:microsoft.quantum.lang-ref.unit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>





## <a name="output--unit"></a><span data-ttu-id="c0ab9-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c0ab9-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

