---
uid: Microsoft.Quantum.MachineLearning.CombinedStructure
title: CombinedStructure függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: CombinedStructure
qsharp.summary: Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.
ms.openlocfilehash: 0a7d66be8b45d6a9df95b425e66b9b6bba241136
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211967"
---
# <a name="combinedstructure-function"></a><span data-ttu-id="9c3f6-102">CombinedStructure függvény</span><span class="sxs-lookup"><span data-stu-id="9c3f6-102">CombinedStructure function</span></span>

<span data-ttu-id="9c3f6-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="9c3f6-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="9c3f6-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="9c3f6-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="9c3f6-105">Egy vagy több szabályozott rotációs réteg esetében egy olyan réteget ad vissza, amelynek a modell-paraméter indexe úgy lett áthelyezve, hogy a különböző rétegek paraméterei eltérő modell-paraméterekkel legyenek megadva.</span><span class="sxs-lookup"><span data-stu-id="9c3f6-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="9c3f6-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9c3f6-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="9c3f6-107">rétegek: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="9c3f6-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="9c3f6-108">A egyesíteni kívánt rétegek.</span><span class="sxs-lookup"><span data-stu-id="9c3f6-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="9c3f6-109">Kimenet: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="9c3f6-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="9c3f6-110">Egyetlen, vezérelt rotációs réteg, amely az összes többi réteg összefűzését jelképezi.</span><span class="sxs-lookup"><span data-stu-id="9c3f6-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>