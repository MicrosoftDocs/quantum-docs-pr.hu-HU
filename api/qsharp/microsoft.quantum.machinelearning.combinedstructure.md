---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: b8ec007202c8e63dc2e98d0c752f6ba1a453e236
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847415"
---
# <a name="combinedstructure-function"></a>CombinedStructure függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Egy vagy több szabályozott rotációs réteg esetében egy olyan réteget ad vissza, amelynek a modell-paraméter indexe úgy lett áthelyezve, hogy a különböző rétegek paraméterei eltérő modell-paraméterekkel legyenek megadva.

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Bevitel

### <a name="layers--controlledrotation"></a>rétegek: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []

A egyesíteni kívánt rétegek.



## <a name="output--controlledrotation"></a>Kimenet: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Egyetlen, vezérelt rotációs réteg, amely az összes többi réteg összefűzését jelképezi.

## <a name="example"></a>Példa

A következők egyenértékűek:

```qsharp
let structure = CombinedStructure([
    LocalRotationLayer(2, PauliY),
    CyclicEntanglingLayer(3, PauliX, 2)
]);
let structure = [
    ControlledRotation((0, new Int[0]), PauliY, 0),
    ControlledRotation((1, new Int[0]), PauliY, 1),
    ControlledRotation((0, [2]), PauliX, 2),
    ControlledRotation((1, [0]), PauliX, 3),
    ControlledRotation((2, [1]), PauliX, 4)
];
```