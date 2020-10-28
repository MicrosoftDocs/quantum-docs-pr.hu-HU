---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: ApplyToMostC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a5927f6b296dd50afec8979c8e8ac22979b8a082
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717169"
---
# <a name="applytomostc-operation"></a>ApplyToMostC művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egy művelet egy tömb utolsó elemére vonatkozik.

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a>Leírás

A művelet `op` és a célok tömbje `targets` érvényes `op(Most(targets))` .

## <a name="input"></a>Bevitel

### <a name="op--t--unit-ctl"></a>op: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit) CTL

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
- [Microsoft. Quantum. Canon. ApplyToMostCA](xref:Microsoft.Quantum.Canon.ApplyToMostCA)