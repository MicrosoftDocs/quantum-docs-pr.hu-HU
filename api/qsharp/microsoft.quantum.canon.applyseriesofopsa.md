---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsA
title: ApplySeriesOfOpsA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint)
ms.openlocfilehash: 052cb52d4ee6500e60043ab7f808497058924afe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844664"
---
# <a name="applyseriesofopsa-operation"></a>ApplySeriesOfOpsA művelet

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy tömbön egymás után az Ops és a célok listáját alkalmazza. (Adjoint)

```qsharp
operation ApplySeriesOfOpsA<'T> (listOfOps : ('T[] => Unit is Adj)[], targets : Int[][], register : 'T[]) : Unit is Adj
```


## <a name="input"></a>Bevitel

### <a name="listofops--t--unit--is-adj"></a>listOfOps: 'T [] => [egység](xref:microsoft.quantum.lang-ref.unit)  []

Azon Ops listája, amelyek mindegyike nem tömböt vesz fel az alkalmazásba. A rendszer szekvenciálisan alkalmazza őket, először a legalacsonyabb indexet.
Mindegyiknek rendelkeznie kell egy adjoint-bejelentkezővel


### <a name="targets--int"></a>célok: [int](xref:microsoft.quantum.lang-ref.int)[] []

Az op céljait leíró beágyazott tömbök. Minden tömbnek tartalmaznia kell a használni kívánt indexeket leíró csoportcsomagból listáját.


### <a name="register--t"></a>Regisztráció: 'T []

A Qubit-regisztrációt kell követni.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem



## <a name="example"></a>Példa

A következők az exp ([PauliX, Pauliy], 0,5) értékre vonatkoznak, hogy qubits a 0, 1//, majd X qubit 2 let Ops = [exp ([PauliX, Pauliy], 0,5, _), ApplyToFirstQubitA (X, _)]; indexek kihagyhatása = [[0, 1], [2]]; ApplySeriesOfOpsA (Ops, indexek, qubitArray);

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Canon. ApplyOpRepeatedlyOver](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)