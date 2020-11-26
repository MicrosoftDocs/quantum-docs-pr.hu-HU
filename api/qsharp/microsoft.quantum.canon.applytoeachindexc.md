---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexC
title: ApplyToEachIndexC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexC
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `C` indicates that the single-qubit operation is controllable.
ms.openlocfilehash: 38fa23c70965118f1787f156bd617d6e967aba05
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217662"
---
# <a name="applytoeachindexc-operation"></a>ApplyToEachIndexC művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egyetlen qubit műveletet alkalmaz a tételjegyzék minden indexelt elemére.
A módosító `C` azt jelzi, hogy az qubit művelet ellenőrizhető.

```qsharp
operation ApplyToEachIndexC<'T> (singleElementOperation : ((Int, 'T) => Unit is Ctl), register : 'T[]) : Unit is Ctl
```


## <a name="input"></a>Bevitel

### <a name="singleelementoperation--intt--unit--is-ctl"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL

Az egyes qubit alkalmazandó művelet.


### <a name="register--t"></a>Regisztráció: 'T []

Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A cél, amelyen az egyes műveletek működnek.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyToEachIndex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)