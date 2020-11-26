---
uid: Microsoft.Quantum.Canon.ApplyToEachIndexA
title: ApplyToEachIndexA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToEachIndexA
qsharp.summary: Applies a single-qubit operation to each indexed element in a register. The modifier `A` indicates that the single-qubit operation is adjointable.
ms.openlocfilehash: e3ff812f14181e676fddf436af8a14f9a58271ec
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217594"
---
# <a name="applytoeachindexa-operation"></a>ApplyToEachIndexA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egyetlen qubit műveletet alkalmaz a tételjegyzék minden indexelt elemére.
A módosító `A` azt jelzi, hogy az qubit művelet adjointable.

```qsharp
operation ApplyToEachIndexA<'T> (singleElementOperation : ((Int, 'T) => Unit is Adj), register : 'T[]) : Unit is Adj
```


## <a name="input"></a>Bevitel

### <a name="singleelementoperation--intt--unit--is-adj"></a>singleElementOperation: ([int](xref:microsoft.quantum.lang-ref.int), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)

Az egyes qubit alkalmazandó művelet.


### <a name="register--t"></a>Regisztráció: 'T []

Azon qubits tömbje, amelyeken alkalmazni kell a megadott műveletet.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A cél, amelyen az egyes műveletek működnek.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyToEachIndex](xref:Microsoft.Quantum.Canon.ApplyToEachIndex)