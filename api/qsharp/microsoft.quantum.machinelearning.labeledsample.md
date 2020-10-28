---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711331"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="37d50-102">LabeledSample-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="37d50-102">LabeledSample user defined type</span></span>

<span data-ttu-id="37d50-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="37d50-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="37d50-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="37d50-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="37d50-105">Egy minta, amely egy olyan osztállyal van megjelölve, amelyhez ez a minta tartozik.</span><span class="sxs-lookup"><span data-stu-id="37d50-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="37d50-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="37d50-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="37d50-107">Szolgáltatások: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="37d50-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="37d50-108">Az adott minta funkcióinak vektora.</span><span class="sxs-lookup"><span data-stu-id="37d50-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="37d50-109">Címke: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="37d50-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="37d50-110">Egy egész szám felirat ahhoz az osztályhoz, amelyhez ez a minta tartozik.</span><span class="sxs-lookup"><span data-stu-id="37d50-110">An integer label for the class to which this sample belongs.</span></span>