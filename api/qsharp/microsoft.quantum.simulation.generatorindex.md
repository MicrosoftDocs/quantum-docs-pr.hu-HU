---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: GeneratorIndex-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 762dac81ea0963443f0338cea1b879856c84b0ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858380"
---
# <a name="generatorindex-user-defined-type"></a>GeneratorIndex-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egyetlen primitív kifejezést képvisel az összes dinamikus generátor készletében, például a Hermitian operátorok esetében, amelyekhez az adott generátor által adott idő-evolúciós folyamaton alapuló Térkép áll rendelkezésre `EvolutionSet` .

Az első elem (int [], Double []) indexeli ezt az egyszeri kifejezést – például a 0,5-as együtthatóval rendelkező XXY-karakterláncot ([1, 1, 2], [0,5]) indexeli. Azt is megteheti, hogy egy folytonos változó (például X cos φ + Y Sin φ) által Hamiltonians paramétert a (z) ([], [φ]) által reprezentált példány lehet. A második elem indexeli azt az alrendszert, amelyen a létrehozó működik.

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="example"></a>Példa

A használatával a (z  <xref:microsoft.quantum.simulation.paulievolutionset> ) $ \pi X_2 X_5 Y_9 $ operátor a következőképpen jelenik meg:

```qsharp
let index = GeneratorIndex(([1, 1, 2], [PI()]), [2, 5, 9]);
```

## <a name="remarks"></a>Megjegyzések

> [!WARNING]
> Az an értelmezése nincs `GeneratorIndex` definiálva, kivéve a generátorok adott készletére mutató hivatkozást.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. szimulációs. EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [Microsoft. Quantum. szimulációs. PauliEvolutionSet](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)