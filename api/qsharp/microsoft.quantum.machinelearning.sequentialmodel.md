---
uid: Microsoft.Quantum.MachineLearning.SequentialModel
title: SequentialModel-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: SequentialModel
qsharp.summary: Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.
ms.openlocfilehash: a425d2155489384ca81ef1c00a5e842bcfb40ae7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722394"
---
# <a name="sequentialmodel-user-defined-type"></a><span data-ttu-id="85a1e-102">SequentialModel-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="85a1e-102">SequentialModel user defined type</span></span>

<span data-ttu-id="85a1e-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="85a1e-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="85a1e-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="85a1e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="85a1e-105">A paraméteres és vezérelt Forgások sorozatából álló Quantum osztályozó modellt ismerteti, amely elforgatási szögek hozzárendelését, valamint a modell által felismert két osztály közötti torzítást tartalmaz.</span><span class="sxs-lookup"><span data-stu-id="85a1e-105">Describes a quantum classifier model composed of a sequence of parameterized and controlled rotations, an assignment of rotation angles, and a bias between the two classes recognized by the model.</span></span>

```qsharp

newtype SequentialModel = (Structure : Microsoft.Quantum.MachineLearning.ControlledRotation[], Parameters : Double[], Bias : Double);
```



## <a name="named-items"></a><span data-ttu-id="85a1e-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="85a1e-106">Named Items</span></span>

### <a name="structure--controlledrotation"></a><span data-ttu-id="85a1e-107">Struktúra: [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="85a1e-107">Structure : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="85a1e-108">A bemenetek besorolásához használt vezérelt forgatások sora.</span><span class="sxs-lookup"><span data-stu-id="85a1e-108">The sequence of controlled rotations used to classify inputs.</span></span>
### <a name="parameters--double"></a><span data-ttu-id="85a1e-109">Paraméterek: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="85a1e-109">Parameters : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="85a1e-110">Rotációs szögek hozzárendelése a megadott besorolási struktúrához.</span><span class="sxs-lookup"><span data-stu-id="85a1e-110">An assignment of rotation angles to the given classification structure.</span></span>
### <a name="bias--double"></a><span data-ttu-id="85a1e-111">Torzítás: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="85a1e-111">Bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="85a1e-112">Az osztályozó által felismert két osztály közötti torzítás.</span><span class="sxs-lookup"><span data-stu-id="85a1e-112">The bias between the two classes recognized by this classifier.</span></span>

## <a name="references"></a><span data-ttu-id="85a1e-113">Referencia</span><span class="sxs-lookup"><span data-stu-id="85a1e-113">References</span></span>

- [<span data-ttu-id="85a1e-114">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="85a1e-114">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)