---
uid: Microsoft.Quantum.Measurement.MeasureWithScratch
title: MeasureWithScratch művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasureWithScratch
qsharp.summary: Measures the given Pauli operator using an explicit scratch qubit to perform the measurement.
ms.openlocfilehash: 1ee25dbccd5bddde406cf8ed84dff77d96d7804e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720328"
---
# <a name="measurewithscratch-operation"></a>MeasureWithScratch művelet

Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)

Csomag [](https://nuget.org/packages/)


A megadott Pauli-operátort egy explicit qubit használatával méri a mérés végrehajtásához.

```qsharp
operation MeasureWithScratch (pauli : Pauli[], target : Qubit[]) : Result
```


## <a name="input"></a>Bevitel

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Egy qubit Pauli-operátorok tömbje megadott több qubit Pauli-operátor.


### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A Qubit-regisztrációt kell mérni.



## <a name="output--__invalidresult__"></a>Kimenet: __érvénytelen <Result>__

Az adott Pauli-operátornak a regisztráción való mérésének eredménye `target` .