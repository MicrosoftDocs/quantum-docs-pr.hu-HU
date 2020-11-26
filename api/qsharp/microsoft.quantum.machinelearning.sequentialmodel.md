---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: 3afdb8dafe0179535fe5d8c3dff668f1f3de2f7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196174"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="741a7-102">SequentialModel-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="741a7-102">SequentialModel user defined type</span></span>

<span data-ttu-id="741a7-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="741a7-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="741a7-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="741a7-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="741a7-105">A paraméteres és vezérelt Forgások sorozatából álló Quantum osztályozó modellt ismerteti, amely elforgatási szögek hozzárendelését, valamint a modell által felismert két osztály közötti torzítást tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="741a7-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="741a7-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="741a7-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="741a7-107">Struktúra: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="741a7-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="741a7-108">A bemenetek besorolásához használt vezérelt forgatások sora.</span><span class="sxs-lookup"><span data-stu-id="741a7-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="741a7-109">Paraméterek: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="741a7-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="741a7-110">Rotációs szögek hozzárendelése a megadott besorolási struktúrához.</span><span class="sxs-lookup"><span data-stu-id="741a7-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="741a7-111">Torzítás: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="741a7-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="741a7-112">Az osztályozó által felismert két osztály közötti torzítás.</span><span class="sxs-lookup"><span data-stu-id="741a7-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="741a7-113">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="741a7-113">References</span></span>

- [<span data-ttu-id="741a7-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="741a7-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)