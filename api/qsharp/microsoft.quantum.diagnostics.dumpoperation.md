---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: 444d42e2440b30b3bdf50d55a399568bed063222
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712857"
---
# <a name="dumpoperation-operation"></a>DumpOperation művelet

Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Csomag [](https://nuget.org/packages/)


A művelet végrehajtásakor az aktuális végrehajtási cél által elérhetővé tett művelet diagnosztika jelenik meg.

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Bevitel

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Azon qubits száma, amelyeken a megadott művelet működik.


### <a name="op--qubit--unit-adj"></a>op: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) – Adj

A diagnosztizálni kívánt művelet.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A művelet meghívása nem befolyásolható a Q #-on belül. Ha vannak ilyenek, a pontos diagnosztika az aktuális végrehajtási cél és a szerkesztő környezettől függ.
Ha például a teljes állapotú kvantum-szimulátort használja, megjelenik egy, a jelöléshez használt egységes mátrix `op` .

Vegye figyelembe, hogy ha olyan szimulátorokon fut, amelyek globális fázist (például a teljes állapotú szimulátort) fogadnak el, a visszaküldött adatábrázolások globális fázisban is változhatnak.

Hasonlóképpen, a sorok és oszlopok mátrix-ábrázolások sorrendje eltérő lehet a műveletet támogató egyes szimulátorok által használt konvenciókkal.