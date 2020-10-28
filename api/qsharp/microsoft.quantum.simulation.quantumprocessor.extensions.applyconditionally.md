---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionally
title: ApplyConditionally művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionally
qsharp.summary: ''
ms.openlocfilehash: fe623b240e35ee88f673b6e90db6307ef701d049
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710533"
---
# <a name="applyconditionally-operation"></a>ApplyConditionally művelet

Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Csomag [](https://nuget.org/packages/)




```qsharp
operation ApplyConditionally<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit), equalArg : 'T), (onNonEqualOp : ('U => Unit), nonEqualArg : 'U)) : Unit
```


## <a name="input"></a>Bevitel

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __érvénytelen <Result>__ []




### <a name="resultsvalues--__invalidresult__"></a>resultsValues: __érvénytelen <Result>__ []




### <a name="onequalop--t--unit"></a>onEqualOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) 




### <a name="equalarg--t"></a>equalArg: nem




### <a name="onnonequalop--u--unit"></a>onNonEqualOp: ' U => [egység](xref:microsoft.quantum.lang-ref.unit) 




### <a name="nonequalarg--u"></a>nonEqualArg: ' U





## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem


### <a name="u"></a>' U

