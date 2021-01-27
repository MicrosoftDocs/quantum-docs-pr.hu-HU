---
uid: Microsoft.Quantum.Canon.ApplyToEachCA
title: ApplyToEachCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachCA
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `CA` indicates that the single-qubit operation is controllable and adjointable.
ms.openlocfilehash: c85b33760eba8d10d9650be2f8306e4afdd1f307
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841485"
---
# <a name="applytoeachca-operation"></a>ApplyToEachCA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egyetlen qubit műveletet alkalmaz a tételjegyzék minden elemére.
A módosító `CA` azt jelzi, hogy az qubit művelet ellenőrizhető és adjointable.

```qsharp
operation ApplyToEachCA<'T> (singleElementOperation : ('T => Unit is Adj + Ctl), register : 'T[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="singleelementoperation--t--unit--is-adj--ctl"></a>singleElementOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

Az egyes qubit alkalmazandó művelet.


### <a name="register--t"></a>Regisztráció: 'T []

Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az a cél, amelyen a művelet működik.

## <a name="example"></a>Példa

Készítse elő a három qubit $ \ket{+} $ állapotot:

```qsharp
using (register = Qubit[3]) {
    ApplyToEach(H, register);
}
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)