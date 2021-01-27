---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA
title: ApplyToFirstThreeQubitsCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsCA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 9bc5248b5de0db60f54bbec4cb33dde1160c2b41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841380"
---
# <a name="applytofirstthreequbitsca-operation"></a>ApplyToFirstThreeQubitsCA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy műveletet alkalmaz a regisztráció első három qubits.
A módosító `CA` azt jelzi, hogy a művelet ellenőrizhető és adjointable.

```qsharp
operation ApplyToFirstThreeQubitsCA (op : ((Qubit, Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="op--qubitqubitqubit--unit--is-adj--ctl"></a>op: ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

Az első három qubits alkalmazandó művelet


### <a name="register--qubit"></a>Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit a tömböt arra az első három qubits, amelynek a műveletét alkalmazza a rendszer.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Ez egyenértékű a következővel:

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyToFirstThreeQubits](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)