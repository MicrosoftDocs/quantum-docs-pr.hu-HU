---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: ApplySeriesOfOpsC művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: eaa0ea3e33cce708af5879cfbe875397fbb82a8a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217934"
---
# <a name="applyseriesofopsc-operation"></a>ApplySeriesOfOpsC művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy tömbön egymás után az Ops és a célok listáját alkalmazza. Ellenőrzött

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit is Ctl
```


## <a name="input"></a>Bevitel

### <a name="listofops--t--unit--is-ctl"></a>listOfOps: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL []

Azon Ops listája, amelyek mindegyike nem tömböt vesz fel az alkalmazásba. A rendszer szekvenciálisan alkalmazza őket, először a legalacsonyabb indexet.
Mindegyiknek rendelkeznie kell egy vezérelt


### <a name="targets--int"></a>célok: [int](xref:microsoft.quantum.lang-ref.int)[] []

Az op céljait leíró beágyazott tömbök. Minden tömbnek tartalmaznia kell a használni kívánt indexeket leíró csoportcsomagból listáját.


### <a name="register--t"></a>Regisztráció: 'T []

A Qubit-regisztrációt kell követni.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem



## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)