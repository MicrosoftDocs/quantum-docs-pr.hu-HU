---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubits
title: ApplyToFirstThreeQubits művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubits
qsharp.summary: Applies an operation to the first three qubits in the register.
ms.openlocfilehash: 61330f9e9b1f6b9f3965c9240505814b295aaefe
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717379"
---
# <a name="applytofirstthreequbits-operation"></a>ApplyToFirstThreeQubits művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egy műveletet alkalmaz a regisztráció első három qubits.

```qsharp
operation ApplyToFirstThreeQubits (op : ((Qubit, Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="op--qubitqubitqubit--unit"></a>op: ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [egység](xref:microsoft.quantum.lang-ref.unit) 

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

- [Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsC](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC)
- [Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsA](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsA)
- [Microsoft. Quantum. Canon. ApplyToFirstThreeQubitsCA](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA)