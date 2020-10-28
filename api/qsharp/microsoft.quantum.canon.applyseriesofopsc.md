---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: ApplySeriesOfOpsC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: d909aadbfe86f6d1314e9be5434249c40932ae4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717645"
---
# <a name="applyseriesofopsc-operation"></a>ApplySeriesOfOpsC művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egy tömbön egymás után az Ops és a célok listáját alkalmazza. Ellenőrzött

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="listofops--t--unit-ctl"></a>listOfOps: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit) CTL []

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