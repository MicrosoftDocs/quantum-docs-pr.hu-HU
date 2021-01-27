---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: 231afe65da3640218cbc97b9d49eae21bf6e1786
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847397"
---
# <a name="controlledrotation-user-defined-type"></a>ControlledRotation-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Egy vezérelt rotációt mutat be a cél és a vezérlési indexek, a rotációs tengely és az index között a modell paraméterének vektora alapján.

```qsharp

newtype ControlledRotation = ((TargetIndex : Int, ControlIndices : Int[]), Axis : Pauli, ParameterIndex : Int);
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="targetindex--int"></a>TargetIndex: [int](xref:microsoft.quantum.lang-ref.int)

Az ellenőrzött forgatás céljának qubit indexe.
### <a name="controlindices--int"></a>ControlIndices: [int](xref:microsoft.quantum.lang-ref.int)[]

Az adott rotációs vezérlő qubit indexei tömbje.
### <a name="axis--pauli"></a>Tengely: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

A forgatás tengelye
### <a name="parameterindex--int"></a>ParameterIndex: [int](xref:microsoft.quantum.lang-ref.int)

A modell paraméterének vektoros indexe, amely a forgatás szögét írja le.

## <a name="example"></a>Példa

Az alábbiakban a regiszter első qubit $X $ tengelyére, a második qubit való vezérlésre, valamint a soros modell negyedik paramétere által megadott szögre vonatkozik:

```qsharp
let controlledRotation = ControlledRotation(
    (0, [1]),
    PauliX,
    3
)
```

## <a name="remarks"></a>Megjegyzések

A nem vezérelt Forgások az `ControlIndices` indexek üres tömbje számára állíthatók be `new Int[0]` .