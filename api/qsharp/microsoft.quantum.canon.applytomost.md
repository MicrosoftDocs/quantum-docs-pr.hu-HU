---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: ApplyToMost művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 7e7824b431ccff644cf5cc53145163327eb8ad36
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208533"
---
# <a name="applytomost-operation"></a>ApplyToMost művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy művelet egy tömb utolsó elemére vonatkozik.

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a>Leírás

A művelet `op` és a célok tömbje `targets` érvényes `op(Most(targets))` .

## <a name="input"></a>Bevitel

### <a name="op--t--unit"></a>op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit) 

Egy alkalmazni kívánt művelet.


### <a name="targets--t"></a>célok: 'T []

A célok tömbje, amelyből az összes, de az utolsó lesz alkalmazva `op` .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az alkalmazni kívánt művelet bemeneti típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyToMostA](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [Microsoft. Quantum. Canon. ApplyToMostC](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [Microsoft. Quantum. Canon. ApplyToMostCA](xref:Microsoft.Quantum.Canon.ApplyToMostCA)