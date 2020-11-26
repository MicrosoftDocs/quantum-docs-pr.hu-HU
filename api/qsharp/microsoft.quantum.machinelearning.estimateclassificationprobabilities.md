---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: EstimateClassificationProbabilities művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 1cd56f6a6483b00afb168f8d84301e73eae9af65
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211899"
---
# <a name="estimateclassificationprobabilities-operation"></a><span data-ttu-id="283f2-102">EstimateClassificationProbabilities művelet</span><span class="sxs-lookup"><span data-stu-id="283f2-102">EstimateClassificationProbabilities operation</span></span>

<span data-ttu-id="283f2-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="283f2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="283f2-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="283f2-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="283f2-105">Egy minta és egy szekvenciális osztályozó alapján a minták besorolási valószínűségét az egyes mintákon az osztályozó kimenetének ismételt mérésével becsüli meg.</span><span class="sxs-lookup"><span data-stu-id="283f2-105">Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.</span></span>

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="283f2-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="283f2-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="283f2-107">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="283f2-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="283f2-108">Az a tűréshatár, amely lehetővé teszi a minta kódolását az állapot-előkészítési műveletben.</span><span class="sxs-lookup"><span data-stu-id="283f2-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="283f2-109">modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="283f2-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="283f2-110">Az adott minták besorolási valószínűségének becslésére szolgáló szekvenciális modell.</span><span class="sxs-lookup"><span data-stu-id="283f2-110">The sequential model to be used to estimate the classification probabilities for the given samples.</span></span>


### <a name="samples--double"></a><span data-ttu-id="283f2-111">minták: [Double](xref:microsoft.quantum.lang-ref.double)[] []</span><span class="sxs-lookup"><span data-stu-id="283f2-111">samples : [Double](xref:microsoft.quantum.lang-ref.double)[][]</span></span>

<span data-ttu-id="283f2-112">A besorolni kívánt mintákhoz tartozó szolgáltatás-vektorok tömbje.</span><span class="sxs-lookup"><span data-stu-id="283f2-112">An array of feature vectors for each sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="283f2-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="283f2-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="283f2-114">A besorolási valószínűség becslése során használandó mérések száma.</span><span class="sxs-lookup"><span data-stu-id="283f2-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="283f2-115">Kimenet: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="283f2-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="283f2-116">Az egyes minták besorolási valószínűségére vonatkozó becslések egy tömbje.</span><span class="sxs-lookup"><span data-stu-id="283f2-116">An array of estimates of the classification probability for each given sample.</span></span>