---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 42bfab7fd1f9372d9394f2eaf2d698b39b4307e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211491"
---
# <a name="validationresults-user-defined-type"></a><span data-ttu-id="b6915-102">ValidationResults-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="b6915-102">ValidationResults user defined type</span></span>

<span data-ttu-id="b6915-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b6915-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b6915-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b6915-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="b6915-105">Az eredmények egy adott minta alapján osztályozták a besorolást.</span><span class="sxs-lookup"><span data-stu-id="b6915-105">The results from having validated a classifier against a set of samples.</span></span>

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a><span data-ttu-id="b6915-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="b6915-106">Named Items</span></span>

### <a name="nmisclassifications--int"></a><span data-ttu-id="b6915-107">NMisclassifications: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b6915-107">NMisclassifications : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b6915-108">Az érvényesítés során megfigyelt téves besorolások száma.</span><span class="sxs-lookup"><span data-stu-id="b6915-108">The number of misclassifications observed during validation.</span></span>
### <a name="nvalidationsamples--int"></a><span data-ttu-id="b6915-109">NValidationSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b6915-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

