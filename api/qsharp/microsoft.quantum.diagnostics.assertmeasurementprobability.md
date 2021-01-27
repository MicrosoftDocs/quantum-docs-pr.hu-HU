---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurementProbability
title: AssertMeasurementProbability művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurementProbability
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.
ms.openlocfilehash: 2fd89121516ef6994dedb75b214589b4e360ff8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830825"
---
# <a name="assertmeasurementprobability-operation"></a>AssertMeasurementProbability művelet

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Azt állítja be, hogy a megadott Pauli-alapú qubits mérése a megadott valószínűséggel az adott küszöbértéken belül megtörténik.

```qsharp
operation AssertMeasurementProbability (bases : Pauli[], qubits : Qubit[], result : Result, prob : Double, msg : String, tol : Double) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="bases--pauli"></a>alapok: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

A több qubit Pauli-operátor valószínűségének meghatározására szolgáló mérési hatás.


### <a name="qubits--qubit"></a>qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A regisztráció, amelyre az állítást el kell végezni.


### <a name="result--__invalidresult__"></a>eredmény: __érvénytelen <Result>__

A várt eredmény `Measure(bases, qubits)` .


### <a name="prob--double"></a>prob: [dupla](xref:microsoft.quantum.lang-ref.double)

A valószínűség, amellyel a rendszer a megadott eredményt várta.


### <a name="msg--string"></a>msg: [sztring](xref:microsoft.quantum.lang-ref.string)

Az az üzenet, amelyet jelenteni kell, ha az állítás sikertelen.


### <a name="tol--double"></a>tol: [dupla](xref:microsoft.quantum.lang-ref.double)





## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Példa

```qsharp
using (register = Qubit()) {
    H(register);
    AssertProb([PauliZ], [register], One, 0.5,
        "Measuring in conjugate basis did not give 50/50 results.", 1e-5);
}
```

## <a name="remarks"></a>Megjegyzések

Vegye figyelembe, hogy a művelet Adjoint és ellenőrzött verziói nem ellenőrzik a feltételt.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Diagnostics. AssertMeasurement](xref:Microsoft.Quantum.Diagnostics.AssertMeasurement)