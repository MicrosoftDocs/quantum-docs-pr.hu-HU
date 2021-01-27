---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: ab9c121884e489b5d056285008c91c1ad70bb053
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854891"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="9d534-102">SequentialModel-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="9d534-102">SequentialModel user defined type</span></span>

<span data-ttu-id="9d534-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="9d534-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="9d534-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="9d534-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="9d534-105">A paraméteres és vezérelt Forgások sorozatából álló Quantum osztályozó modellt ismerteti, amely elforgatási szögek hozzárendelését, valamint a modell által felismert két osztály közötti torzítást tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="9d534-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="9d534-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="9d534-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="9d534-107">Struktúra: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="9d534-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="9d534-108">A bemenetek besorolásához használt vezérelt forgatások sora.</span><span class="sxs-lookup"><span data-stu-id="9d534-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="9d534-109">Paraméterek: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="9d534-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="9d534-110">Rotációs szögek hozzárendelése a megadott besorolási struktúrához.</span><span class="sxs-lookup"><span data-stu-id="9d534-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="9d534-111">Torzítás: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9d534-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9d534-112">Az osztályozó által felismert két osztály közötti torzítás.</span><span class="sxs-lookup"><span data-stu-id="9d534-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="9d534-113">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="9d534-113">References</span></span>

- [<span data-ttu-id="9d534-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="9d534-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)