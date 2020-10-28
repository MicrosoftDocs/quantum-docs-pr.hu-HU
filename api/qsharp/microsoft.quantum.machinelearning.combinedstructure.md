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
# <a name="combinedstructure-function"></a><span data-ttu-id="be5ed-102">CombinedStructure függvény</span><span class="sxs-lookup"><span data-stu-id="be5ed-102">CombinedStructure function</span></span>

<span data-ttu-id="be5ed-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="be5ed-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="be5ed-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="be5ed-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="be5ed-105">Egy vagy több szabályozott rotációs réteg esetében egy olyan réteget ad vissza, amelynek a modell-paraméter indexe úgy lett áthelyezve, hogy a különböző rétegek paraméterei eltérő modell-paraméterekkel legyenek megadva.</span><span class="sxs-lookup"><span data-stu-id="be5ed-105">Given one or more layers of controlled rotations, returns a single layer with model parameter index shifted such that distinct layers are parameterized by distinct model parameters.</span></span>

```qsharp
function CombinedStructure (layers : Microsoft.Quantum.MachineLearning.ControlledRotation[][]) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="be5ed-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="be5ed-106">Input</span></span>

### <a name="layers--controlledrotation"></a><span data-ttu-id="be5ed-107">rétegek: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[] []</span><span class="sxs-lookup"><span data-stu-id="be5ed-107">layers : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[][]</span></span>

<span data-ttu-id="be5ed-108">A egyesíteni kívánt rétegek.</span><span class="sxs-lookup"><span data-stu-id="be5ed-108">The layers to be combined.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="be5ed-109">Kimenet: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="be5ed-109">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="be5ed-110">Egyetlen, vezérelt rotációs réteg, amely az összes többi réteg összefűzését jelképezi.</span><span class="sxs-lookup"><span data-stu-id="be5ed-110">A single layer of controlled rotations, representing the concatenation of all other layers.</span></span>