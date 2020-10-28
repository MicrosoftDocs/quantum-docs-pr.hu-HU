---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyIntrinsicCA
title: ApplyConditionallyIntrinsicCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyIntrinsicCA
qsharp.summary: ''
ms.openlocfilehash: 7cdddba45824d5e5037270d8578f2cb16c03be83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720136"
---
# <a name="applyconditionallyintrinsicca-operation"></a>ApplyConditionallyIntrinsicCA művelet

Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Csomag [](https://nuget.org/packages/)




```qsharp
operation ApplyConditionallyIntrinsicCA (measurementResults : Result[], resultsValues : Result[], onEqualOp : (Unit => Unit is Ctl + Adj), onNonEqualOp : (Unit => Unit is Ctl + Adj)) : Unit
```


## <a name="input"></a>Bevitel

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __érvénytelen <Result>__ []




### <a name="resultsvalues--__invalidresult__"></a>resultsValues: __érvénytelen <Result>__ []




### <a name="onequalop--unit--unit-ctl--adj"></a>onEqualOp: [egység](xref:microsoft.quantum.lang-ref.unit) => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj




### <a name="onnonequalop--unit--unit-ctl--adj"></a>onNonEqualOp: [egység](xref:microsoft.quantum.lang-ref.unit) => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj





## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

