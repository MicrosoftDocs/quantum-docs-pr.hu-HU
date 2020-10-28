---
uid: Microsoft.Quantum.MachineLearning.PartialRotationsLayer
title: PartialRotationsLayer függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: PartialRotationsLayer
qsharp.summary: Returns an array of single-qubit rotations along a given axis, parameterized by distinct model parameters.
ms.openlocfilehash: ab964d2c43a13a5daf64aefdeccd1c26cd371ff4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722436"
---
# <a name="partialrotationslayer-function"></a>PartialRotationsLayer függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


Egy qubit-forgás tömbjét adja vissza egy adott tengelyen, a paramétert pedig a különböző modell paraméterekkel együtt.

```qsharp
function PartialRotationsLayer (idxsQubits : Int[], axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Bevitel

### <a name="idxsqubits--int"></a>idxsQubits: [int](xref:microsoft.quantum.lang-ref.int)[]

A qubits az egyes rotációs célokhoz használandó indexek.


### <a name="axis--pauli"></a>tengely: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Az adott réteg minden egyes forgásának rotációs tengelye



## <a name="output--controlledrotation"></a>Kimenet: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

A megadott tengelyre vonatkozó vezérelt rotációs tömb, amely az egyes `nQubits` qubits.