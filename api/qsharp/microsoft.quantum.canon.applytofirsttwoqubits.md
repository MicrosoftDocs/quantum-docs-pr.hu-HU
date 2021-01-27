---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: ApplyToFirstTwoQubits művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: c89ea89c055a950a9aee533653d40c84d8e179da
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841370"
---
# <a name="applytofirsttwoqubits-operation"></a>ApplyToFirstTwoQubits művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy műveletet alkalmaz a regisztráció első két qubits.

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="op--qubitqubit--unit"></a>op: ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [egység](xref:microsoft.quantum.lang-ref.unit) 

Az első két qubits alkalmazandó művelet


### <a name="register--qubit"></a>Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit a tömböt az első két qubits, amelynek a műveletét alkalmazza a rendszer.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Ez egyenértékű a következővel:

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyToFirstTwoQubitsA](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [Microsoft. Quantum. Canon. ApplyToFirstTwoQubitsC](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [Microsoft. Quantum. Canon. ApplyToFirstTwoQubitsCA](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)