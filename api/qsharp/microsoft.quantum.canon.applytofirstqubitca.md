---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: ApplyToFirstQubitCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: ba82199cc7a548d771027141780873c05de71c57
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841434"
---
# <a name="applytofirstqubitca-operation"></a>ApplyToFirstQubitCA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A művelet op-t alkalmazza a regisztráció első qubit.
A módosító `CA` azt jelzi, hogy a művelet ellenőrizhető és adjointable.

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="op--qubit--unit--is-adj--ctl"></a>op: az [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

Az első qubit alkalmazandó művelet


### <a name="register--qubit"></a>Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit-tömb az első Qubit, amelynek a műveletét alkalmazza a rendszer



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyToFirstQubit](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)