---
uid: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions.ApplyConditionallyA
title: ApplyConditionallyA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation.QuantumProcessor.Extensions
qsharp.name: ApplyConditionallyA
qsharp.summary: ''
ms.openlocfilehash: 18ea79e363c28d4fa7aacb69d53a43f6ce39df36
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847875"
---
# <a name="applyconditionallya-operation"></a>ApplyConditionallyA művelet

Névtér: [Microsoft. Quantum. szimulációs. QuantumProcessor. Extensions](xref:Microsoft.Quantum.Simulation.QuantumProcessor.Extensions)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)




```qsharp
operation ApplyConditionallyA<'T, 'U> (measurementResults : Result[], resultsValues : Result[], (onEqualOp : ('T => Unit is Adj), equalArg : 'T), (onNonEqualOp : ('U => Unit is Adj), nonEqualArg : 'U)) : Unit is Adj
```


## <a name="input"></a>Bevitel

### <a name="measurementresults--__invalidresult__"></a>measurementResults: __érvénytelen <Result>__[]




### <a name="resultsvalues--__invalidresult__"></a>resultsValues: __érvénytelen <Result>__[]




### <a name="onequalop--t--unit--is-adj"></a>onEqualOp: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)




### <a name="equalarg--t"></a>equalArg: nem




### <a name="onnonequalop--u--unit--is-adj"></a>onNonEqualOp: ' U => [egység](xref:microsoft.quantum.lang-ref.unit)




### <a name="nonequalarg--u"></a>nonEqualArg: ' U





## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem


### <a name="u"></a>' U

