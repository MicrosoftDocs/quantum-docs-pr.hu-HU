---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyIfZeroA
title: ApplyIfZeroA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyIfZeroA
qsharp.summary: ''
ms.openlocfilehash: 124c5bbabc9e22804734ddbde955312db9655187
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725699"
---
# <a name="applyifzeroa-operation"></a><span data-ttu-id="e1b00-102">ApplyIfZeroA művelet</span><span class="sxs-lookup"><span data-stu-id="e1b00-102">ApplyIfZeroA operation</span></span>

<span data-ttu-id="e1b00-103">Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span><span class="sxs-lookup"><span data-stu-id="e1b00-103">Namespace: [Microsoft.Quantum.Simulation.QuantumProcessor.Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)</span></span>

<span data-ttu-id="e1b00-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e1b00-104">Package: [](https://nuget.org/packages/)</span></span>




```qsharp
operation ApplyIfZeroA<'T> (measurementResult : Result, (onResultZeroOp : ('T => Unit is Adj), zeroArg : 'T)) : Unit
```


## <a name="input"></a><span data-ttu-id="e1b00-105">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e1b00-105">Input</span></span>

### <a name="measurementresult--__invalidresult__"></a><span data-ttu-id="e1b00-106">measurementResult: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="e1b00-106">measurementResult : __invalid<Result>__</span></span>




### <a name="onresultzeroop--t--unit-adj"></a><span data-ttu-id="e1b00-107">onResultZeroOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="e1b00-107">onResultZeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>




### <a name="zeroarg--t"></a><span data-ttu-id="e1b00-108">zeroArg: nem</span><span class="sxs-lookup"><span data-stu-id="e1b00-108">zeroArg : 'T</span></span>





## <a name="output--unit"></a><span data-ttu-id="e1b00-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1b00-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e1b00-110">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e1b00-110">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e1b00-111">Nem</span><span class="sxs-lookup"><span data-stu-id="e1b00-111">'T</span></span>

