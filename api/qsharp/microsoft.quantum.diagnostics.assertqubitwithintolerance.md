---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: AssertQubitWithinTolerance művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 3fe4aa739c5e15199401aecb76ef551e52f6dcff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712884"
---
# <a name="assertqubitwithintolerance-operation"></a>AssertQubitWithinTolerance művelet

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag [](https://nuget.org/packages/)


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