---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bd466ff59e6e962be9a7e58b6d298c60b0d1d90d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717449"
---
# <a name="applytoelementc-operation"></a>ApplyToElementC művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egy műveletet alkalmaz egy tömb egy adott elemére.

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a>Leírás

A művelet `op` , az index `index` és a célok tömbje is `targets` érvényes `op(targets[index])` .

## <a name="input"></a>Bevitel

### <a name="op--t--unit-ctl"></a>op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) CTL

Egy alkalmazni kívánt művelet.


### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)

Egy index a célok tömbje számára.


### <a name="targets--t"></a>célok: 'T []

A lehetséges célpontok tömbje `op` .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az alkalmazni kívánt művelet bemeneti típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyToElement](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [Microsoft. Quantum. Canon. ApplyToElementA](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [Microsoft. Quantum. Canon. ApplyToElementCA](xref:Microsoft.Quantum.Canon.ApplyToElementCA)