---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: ApplySeriesOfOps művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b8810e7d31689046e72905195a3a25ef80fc8d67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218002"
---
# <a name="applyseriesofops-operation"></a>ApplySeriesOfOps művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy tömbön egymás után az Ops és a célok listáját alkalmazza.

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="listofops--t--unit-"></a>listOfOps: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit) []

Azon Ops listája, amelyek mindegyike nem tömböt vesz fel az alkalmazásba. A rendszer szekvenciálisan alkalmazza őket, először a legalacsonyabb indexet.


### <a name="targets--int"></a>célok: [int](xref:microsoft.quantum.lang-ref.int)[] []

Az op céljait leíró beágyazott tömbök. Minden tömbnek tartalmaznia kell a használni kívánt indexeket leíró csoportcsomagból listáját.


### <a name="register--t"></a>Regisztráció: 'T []

A Qubit-regisztrációt kell követni.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem



## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)