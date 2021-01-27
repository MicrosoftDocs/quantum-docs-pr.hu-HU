---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: cde188806506c586c4c77a7f9b2b43ad0e10ef1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829275"
---
# <a name="dumpoperation-operation"></a>DumpOperation művelet

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A művelet végrehajtásakor az aktuális végrehajtási cél által elérhetővé tett művelet diagnosztika jelenik meg.

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Bevitel

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Azon qubits száma, amelyeken a megadott művelet működik.


### <a name="op--qubit--unit--is-adj"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)

A diagnosztizálni kívánt művelet.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Példa

A kvantum-szimulátor célján való futtatáskor a következő kódrészlet kimenetet küld a Matrix $ $ \begin{aligned} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \end{Matrix}\right) \end{aligned}.
$$

```qsharp
operation DumpCnot() : Unit {
    DumpOperation(2, ApplyToFirstTwoQubitsCA(CNOT, _));
}
```

## <a name="remarks"></a>Megjegyzések

A művelet meghívása nem befolyásolható a Q #-on belül. Ha vannak ilyenek, a pontos diagnosztika az aktuális végrehajtási cél és a szerkesztő környezettől függ.
Ha például a teljes állapotú kvantum-szimulátort használja, megjelenik egy, a jelöléshez használt egységes mátrix `op` .

Vegye figyelembe, hogy ha olyan szimulátorokon fut, amelyek globális fázist (például a teljes állapotú szimulátort) fogadnak el, a visszaküldött adatábrázolások globális fázisban is változhatnak.

Hasonlóképpen, a sorok és oszlopok mátrix-ábrázolások sorrendje eltérő lehet a műveletet támogató egyes szimulátorok által használt konvenciókkal.