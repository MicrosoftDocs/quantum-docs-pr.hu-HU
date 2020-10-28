---
uid: Microsoft.Quantum.MachineLearning.ControlledRotation
title: ControlledRotation-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ControlledRotation
qsharp.summary: Describes a controlled rotation in terms of its target and control indices, rotation axis, and index into a model parameter vector.
ms.openlocfilehash: afc425c16ab550fd414e656484c9ff6f0f8f3ef4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711359"
---
# <a name="controlledrotation-user-defined-type"></a>ControlledRotation-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


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

## <a name="remarks"></a>Megjegyzések

A nem vezérelt Forgások az `ControlIndices` indexek üres tömbje számára állíthatók be `new Int[0]` .