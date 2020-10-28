---
uid: Microsoft.Quantum.MachineLearning.CyclicEntanglingLayer
title: CyclicEntanglingLayer függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CyclicEntanglingLayer
qsharp.summary: Returns an array of singly controlled rotations along a given axis, arranged cyclically across a register of qubits, and parameterized by distinct model parameters.
ms.openlocfilehash: 6e0f5057b35baefe2677126ba70ee4fddde7d4db
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720509"
---
# <a name="cyclicentanglinglayer-function"></a>CyclicEntanglingLayer függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


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