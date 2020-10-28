---
uid: Microsoft.Quantum.Measurement.MeasurePaulis
title: MeasurePaulis művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MeasurePaulis
qsharp.summary: Given an array of multi-qubit Pauli operators, measures each using a specified measurement gadget, then returns the array of results.
ms.openlocfilehash: 7348ab3941af391c451d5c66f888cf3b6662cf20
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720341"
---
# <a name="measurepaulis-operation"></a>MeasurePaulis művelet

Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)

Csomag [](https://nuget.org/packages/)


A több qubit Pauli-operátorok tömbje a megadott mérési minialkalmazások alapján méri le az eredményeket, majd visszaadja az eredmények tömbjét.

```qsharp
operation MeasurePaulis (paulis : Pauli[][], target : Qubit[], gadget : ((Pauli[], Qubit[]) => Result)) : Result[]
```


## <a name="input"></a>Bevitel

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Több qubit Pauli-operátorok tömbje.


### <a name="target--qubit"></a>cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Regisztráljon, amelyen az adott operátorok mérhetők.


### <a name="gadget--pauliqubit--__invalidresult__"></a>Gadget: ( [Pauli](xref:microsoft.quantum.lang-ref.pauli)[], [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => __érvénytelen <Result>__ 

Egy adott qubit operátor mérését végző művelet.



## <a name="output--__invalidresult__"></a>Kimenet: __érvénytelen <Result>__ []

Az egyes elemeinek mérési eredményeiből származó eredmények tömbje `paulis` `target` .