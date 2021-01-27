---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: AssertQubitWithinTolerance művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 7f57fc7a29d3eb86dc94cb24230d52b37eb6971d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853434"
---
# <a name="assertqubitwithintolerance-operation"></a>AssertQubitWithinTolerance művelet

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Azt állítja, hogy a qubit a `q` Pauli Z operátor várt eigenstate található, egy adott toleranciával.

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>Bevitel

### <a name="expected--__invalidresult__"></a>várt: __érvénytelen <Result>__

A qubit várható állapota a következő: `Zero` vagy `One` .


### <a name="q--qubit"></a>k: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Az a qubit, amelynek az állapota érvényesítve van.


### <a name="tolerance--double"></a>tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)

A várt eredményt visszaadó qubit mértékének valószínűségére vonatkozó tűréshatár.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> lehetővé teszi tetszőleges qubit-állapotok megadását, nem csak $Z $ eigenstates.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)