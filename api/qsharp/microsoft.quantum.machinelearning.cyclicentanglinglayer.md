---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 5d0af0a60217b69dc7eb8ece8952f2a7f0c09280
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847387"
---
# <a name="cyclicentanglinglayer-function"></a>CyclicEntanglingLayer függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Egy, az adott tengelyen lévő, jól vezérelt rotációs tömböt ad vissza, amelyet ciklikusan rendeznek a qubits-jegyzékben, és különböző modell-paraméterekkel rendelkeznek.

```qsharp
function CyclicEntanglingLayer (nQubits : Int, axis : Pauli, stride : Int) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Bevitel

### <a name="nqubits--int"></a>nQubits: [int](xref:microsoft.quantum.lang-ref.int)

Az adott réteg által lejátszott qubits száma.


### <a name="axis--pauli"></a>tengely: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Az adott réteg minden egyes forgásának rotációs tengelye


### <a name="stride--int"></a>lépéshossz: [int](xref:microsoft.quantum.lang-ref.int)

A cél és a vezérlő indexek közötti elkülönítés az egyes rotációk esetében.



## <a name="output--controlledrotation"></a>Kimenet: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

A kétqubitos vezérelt rotációk tömbje ciklikusan, a qubits-jegyzéken belül van meghatározva `nQubits` .

## <a name="example"></a>Példa

A következők egyenértékűek:

```qsharp
let layer = CyclicEntanglingLayer(3, PauliX, 2);
let layer = [
    ControlledRotation((0, [2]), PauliX, 0),
    ControlledRotation((1, [0]), PauliX, 1),
    ControlledRotation((2, [1]), PauliX, 2)
];
```