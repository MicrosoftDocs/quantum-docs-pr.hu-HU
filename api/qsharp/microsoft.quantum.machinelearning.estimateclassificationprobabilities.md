---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: EstimateClassificationProbabilities művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 2b7845d39256f718cc3e415207b8a47b24620bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709790"
---
# <a name="estimateclassificationprobabilities-operation"></a><span data-ttu-id="06dd0-102">EstimateClassificationProbabilities művelet</span><span class="sxs-lookup"><span data-stu-id="06dd0-102">EstimateClassificationProbabilities operation</span></span>

<span data-ttu-id="06dd0-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="06dd0-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="06dd0-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="06dd0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="06dd0-105">Egy minta és egy szekvenciális osztályozó alapján a minták besorolási valószínűségét az egyes mintákon az osztályozó kimenetének ismételt mérésével becsüli meg.</span><span class="sxs-lookup"><span data-stu-id="06dd0-105">Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.</span></span>

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="06dd0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="06dd0-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="06dd0-107">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="06dd0-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="06dd0-108">Az a tűréshatár, amely lehetővé teszi a minta kódolását az állapot-előkészítési műveletben.</span><span class="sxs-lookup"><span data-stu-id="06dd0-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="06dd0-109">modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="06dd0-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="06dd0-110">Az adott minták besorolási valószínűségének becslésére szolgáló szekvenciális modell.</span><span class="sxs-lookup"><span data-stu-id="06dd0-110">The sequential model to be used to estimate the classification probabilities for the given samples.</span></span>


### <a name="samples--double"></a><span data-ttu-id="06dd0-111">minták: [Double](xref:microsoft.quantum.lang-ref.double)[] []</span><span class="sxs-lookup"><span data-stu-id="06dd0-111">samples : [Double](xref:microsoft.quantum.lang-ref.double)[][]</span></span>

<span data-ttu-id="06dd0-112">A besorolni kívánt mintákhoz tartozó szolgáltatás-vektorok tömbje.</span><span class="sxs-lookup"><span data-stu-id="06dd0-112">An array of feature vectors for each sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="06dd0-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="06dd0-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="06dd0-114">A besorolási valószínűség becslése során használandó mérések száma.</span><span class="sxs-lookup"><span data-stu-id="06dd0-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="06dd0-115">Kimenet: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="06dd0-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="06dd0-116">Az egyes minták besorolási valószínűségére vonatkozó becslések egy tömbje.</span><span class="sxs-lookup"><span data-stu-id="06dd0-116">An array of estimates of the classification probability for each given sample.</span></span>