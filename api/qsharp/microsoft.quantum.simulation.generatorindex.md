---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: GeneratorIndex-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: dae23db9bee34be4aa99d96799efad64a66d7193
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229324"
---
# <a name="generatorindex-user-defined-type"></a>GeneratorIndex-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egyetlen primitív kifejezést képvisel az összes dinamikus generátor készletében, például a Hermitian operátorok esetében, amelyekhez az adott generátor által adott idő-evolúciós folyamaton alapuló Térkép áll rendelkezésre `EvolutionSet` .

Az első elem (int [], Double []) indexeli ezt az egyszeri kifejezést – például a 0,5-as együtthatóval rendelkező XXY-karakterláncot ([1, 1, 2], [0,5]) indexeli. Azt is megteheti, hogy egy folytonos változó (például X cos φ + Y Sin φ) által Hamiltonians paramétert a (z) ([], [φ]) által reprezentált példány lehet. A második elem indexeli azt az alrendszert, amelyen a létrehozó működik.

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="remarks"></a>Megjegyzések

> [!WARNING]
> Az an értelmezése nincs `GeneratorIndex` definiálva, kivéve a generátorok adott készletére mutató hivatkozást.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. szimulációs. EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [Microsoft. Quantum. szimulációs. PauliEvolutionSet](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)