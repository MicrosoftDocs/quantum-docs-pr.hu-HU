---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: fbfd87761a40abe350e5f955fb53d8024eeb614e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720520"
---
# <a name="combinedstructure-function"></a>CombinedStructure függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


Egy vagy több szabályozott rotációs réteg esetében egy olyan réteget ad vissza, amelynek a modell-paraméter indexe úgy lett áthelyezve, hogy a különböző rétegek paraméterei eltérő modell-paraméterekkel legyenek megadva.

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a>Bevitel

### <a name="layers--controlledrotation"></a>rétegek: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []

A egyesíteni kívánt rétegek.



## <a name="output--controlledrotation"></a>Kimenet: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]

Egyetlen, vezérelt rotációs réteg, amely az összes többi réteg összefűzését jelképezi.