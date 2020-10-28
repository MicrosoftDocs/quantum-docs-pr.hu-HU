---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 599a8afe1ab97b0ab0d6621cabd7707faaeddda3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717448"
---
# <a name="applytoelementca-operation"></a>ApplyToElementCA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egy műveletet alkalmaz egy tömb egy adott elemére.

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a>Leírás

A művelet `op` , az index `index` és a célok tömbje is `targets` érvényes `op(targets[index])` .

## <a name="input"></a>Bevitel

### <a name="op--t--unit-adj--ctl"></a>op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL

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
- [Microsoft. Quantum. Canon. ApplyToElementC](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [Microsoft. Quantum. Canon. ApplyToElementA](xref:Microsoft.Quantum.Canon.ApplyToElementA)