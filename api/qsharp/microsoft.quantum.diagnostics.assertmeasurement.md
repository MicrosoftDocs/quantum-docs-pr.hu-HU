---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: AssertMeasurement művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 8f5113f1d6b8e4f104af10ca330e244e95793418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853504"
---
# <a name="assertmeasurement-operation"></a>AssertMeasurement művelet

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Azt állítja be, hogy a megadott Pauli-alapú qubits mérése mindig a megadott eredménnyel jár.

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="bases--pauli"></a>alapok: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

A több qubit Pauli-operátor valószínűségének meghatározására szolgáló mérési hatás.


### <a name="qubits--qubit"></a>qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

A regisztráció, amelyre az állítást el kell végezni.


### <a name="result--__invalidresult__"></a>eredmény: __érvénytelen <Result>__

A várt eredménye `Measure(bases, qubits)` .


### <a name="msg--string"></a>msg: [sztring](xref:microsoft.quantum.lang-ref.string)

Az az üzenet, amelyet jelenteni kell, ha az állítás sikertelen.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Vegye figyelembe, hogy a művelet Adjoint és ellenőrzött verziói nem ellenőrzik a feltételt.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Diagnostics. AssertMeasurementProbability](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)