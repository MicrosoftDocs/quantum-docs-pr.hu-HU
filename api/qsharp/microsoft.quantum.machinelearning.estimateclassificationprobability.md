---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: EstimateClassificationProbability művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 79e40bc4bc0954dc6742307122609950bf22ec71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709776"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="5e5f8-102">EstimateClassificationProbability művelet</span><span class="sxs-lookup"><span data-stu-id="5e5f8-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="5e5f8-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="5e5f8-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="5e5f8-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5e5f8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5e5f8-105">Egy minta és egy szekvenciális osztályozó alapján a rendszer az adott mintában lévő osztályozó kimenetének ismételt mérésével megbecsüli a minta besorolási valószínűségét.</span><span class="sxs-lookup"><span data-stu-id="5e5f8-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="5e5f8-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5e5f8-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="5e5f8-107">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5e5f8-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5e5f8-108">Az a tűréshatár, amely lehetővé teszi a minta kódolását az állapot-előkészítési műveletben.</span><span class="sxs-lookup"><span data-stu-id="5e5f8-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="5e5f8-109">modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="5e5f8-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="5e5f8-110">Az adott minta besorolási valószínűségének becslésére szolgáló szekvenciális modell.</span><span class="sxs-lookup"><span data-stu-id="5e5f8-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="5e5f8-111">minta: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="5e5f8-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="5e5f8-112">A besorolni kívánt minta funkciós vektora.</span><span class="sxs-lookup"><span data-stu-id="5e5f8-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="5e5f8-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5e5f8-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5e5f8-114">A besorolási valószínűség becslése során használandó mérések száma.</span><span class="sxs-lookup"><span data-stu-id="5e5f8-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="5e5f8-115">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5e5f8-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5e5f8-116">Az adott minta besorolási valószínűségének becslése.</span><span class="sxs-lookup"><span data-stu-id="5e5f8-116">An estimate of the classification probability for the given sample.</span></span>