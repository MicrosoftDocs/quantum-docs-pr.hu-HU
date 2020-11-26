---
uid: Microsoft.Quantum.Canon.ApplyToEachC
title: ApplyToEachC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachC
qsharp.summary: Applies a single-qubit operation to each element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 535f815503e20b5cee35f3f273a714203a4baf12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217781"
---
# <a name="applytoeachc-operation"></a>ApplyToEachC művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egyetlen qubit műveletet alkalmaz a tételjegyzék minden elemére.
A módosító `C` azt jelzi, hogy az qubit művelet ellenőrizhető.

```qsharp
operation ApplyToEachC<'T> (singleElementOperation : ('T => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a>Bevitel

### <a name="singleelementoperation--t--unit--is-ctl"></a>singleElementOperation: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL

Az egyes qubit alkalmazandó művelet.


### <a name="register--t"></a>Regisztráció: 'T []

Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az a cél, amelyen a művelet működik.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyToEach](xref:Microsoft.Quantum.Canon.ApplyToEach)