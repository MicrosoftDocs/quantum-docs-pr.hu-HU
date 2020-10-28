---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: ApplyToEachIndexC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 387d7ea24b9251386a71b42a1f51ce70933bf6fc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717532"
---
# <a name="applytoeachindexc-operation"></a>ApplyToEachIndexC művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egyetlen qubit műveletet alkalmaz a tételjegyzék minden indexelt elemére.
A módosító `C` azt jelzi, hogy az qubit művelet ellenőrizhető.

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="singleelementoperation--intt--unit-ctl"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), 't) => [egység](xref:microsoft.quantum.lang-ref.unit) CTL

Az egyes qubit alkalmazandó művelet.


### <a name="register--t"></a>Regisztráció: 'T []

Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A cél, amelyen az egyes műveletek működnek.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyToEachIndex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)