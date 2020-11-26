---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: ApplyToRestC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 779c3831b2027a58f97dae9609e96d4d98247da7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208193"
---
# <a name="applytorestc-operation"></a>ApplyToRestC művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A művelet a tömb első elemére vonatkozik.

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a>Leírás

A művelet `op` és a célok tömbje `targets` érvényes `op(Rest(targets))` .

## <a name="input"></a>Bevitel

### <a name="op--t--unit--is-ctl"></a>op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL

Egy alkalmazni kívánt művelet.


### <a name="targets--t"></a>célok: 'T []

A célok tömbje, amelyből az összes, de az első lesz alkalmazva `op` .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az alkalmazni kívánt művelet bemeneti típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyToRest](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [Microsoft. Quantum. Canon. ApplyToRestA](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [Microsoft. Quantum. Canon. ApplyToRestCA](xref:Microsoft.Quantum.Canon.ApplyToRestCA)