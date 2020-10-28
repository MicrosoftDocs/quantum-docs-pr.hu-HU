---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyC
title: ApplyConditionallyC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyC
qsharp.summary: ''
ms.openlocfilehash: fc1cf50b7befd40cf20720032329438715a9b856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720185"
---
# <a name="applyconditionallyc-operation"></a>ApplyConditionallyC művelet

Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Csomag [](https://nuget.org/packages/)




```qsharp
operation ApplyConditionallyC<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Ctl), equalArg : 'T), (onNonEqualOp : ('U => Unit is Ctl), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a>Bevitel

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __érvénytelen <Result>__ []




### <a name="resultsvalues--__invalidresult__"></a>resultsValues: __érvénytelen <Result>__ []




### <a name="onequalop--t--unit-ctl"></a>onEqualOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) CTL




### <a name="equalarg--t"></a>equalArg: nem




### <a name="onnonequalop--u--unit-ctl"></a>onNonEqualOp: ' U => [egység](xref:microsoft.quantum.lang-ref.unit) CTL




### <a name="nonequalarg--u"></a>nonEqualArg: ' U





## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem


### <a name="u"></a>' U

