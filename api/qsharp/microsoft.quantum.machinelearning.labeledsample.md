---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196327"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="04c5d-102">LabeledSample-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="04c5d-102">LabeledSample user defined type</span></span>

<span data-ttu-id="04c5d-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="04c5d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="04c5d-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="04c5d-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="04c5d-105">Egy minta, amely egy olyan osztállyal van megjelölve, amelyhez ez a minta tartozik.</span><span class="sxs-lookup"><span data-stu-id="04c5d-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="04c5d-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="04c5d-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="04c5d-107">Szolgáltatások: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="04c5d-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="04c5d-108">Az adott minta funkcióinak vektora.</span><span class="sxs-lookup"><span data-stu-id="04c5d-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="04c5d-109">Címke: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="04c5d-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="04c5d-110">Egy egész szám felirat ahhoz az osztályhoz, amelyhez ez a minta tartozik.</span><span class="sxs-lookup"><span data-stu-id="04c5d-110">An integer label for the class to which this sample belongs.</span></span>