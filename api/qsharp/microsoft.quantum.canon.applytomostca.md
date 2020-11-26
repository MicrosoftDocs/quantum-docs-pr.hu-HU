---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: ApplyToMostCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2ce76d2a86665fbfa5f5d91df23220c7c80981e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208414"
---
# <a name="applytomostca-operation"></a>ApplyToMostCA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy művelet egy tömb utolsó elemére vonatkozik.

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a>Leírás

A művelet `op` és a célok tömbje `targets` érvényes `op(Most(targets))` .

## <a name="input"></a>Bevitel

### <a name="op--t--unit--is-adj--ctl"></a>op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

Egy alkalmazni kívánt művelet.


### <a name="targets--t"></a>célok: 'T []

A célok tömbje, amelyből az összes, de az utolsó lesz alkalmazva `op` .



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az alkalmazni kívánt művelet bemeneti típusa.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyToMost](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [Microsoft. Quantum. Canon. ApplyToMostA](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [Microsoft. Quantum. Canon. ApplyToMostC](xref:Microsoft.Quantum.Canon.ApplyToMostC)