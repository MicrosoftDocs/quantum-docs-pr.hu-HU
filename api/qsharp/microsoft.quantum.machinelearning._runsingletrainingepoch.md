---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: _RunSingleTrainingEpoch művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: 2b4f629eac0bd8e60bd4d86077521c60085d4809
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720629"
---
# <a name="_runsingletrainingepoch-operation"></a><span data-ttu-id="c171a-102">_RunSingleTrainingEpoch művelet</span><span class="sxs-lookup"><span data-stu-id="c171a-102">_RunSingleTrainingEpoch operation</span></span>

<span data-ttu-id="c171a-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c171a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c171a-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c171a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c171a-105">Hajtson végre egy időpontot szekvenciális osztályozó képzésen az adatmintaok egy részhalmazán.</span><span class="sxs-lookup"><span data-stu-id="c171a-105">Perform one epoch of sequential classifier training on a subset of data samples.</span></span>

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a><span data-ttu-id="c171a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c171a-106">Input</span></span>

### <a name="encodedsamples--labeledsamplestategenerator"></a><span data-ttu-id="c171a-107">encodedSamples: ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []</span><span class="sxs-lookup"><span data-stu-id="c171a-107">encodedSamples : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator))[]</span></span>




### <a name="schedule--samplingschedule"></a><span data-ttu-id="c171a-108">Schedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="c171a-108">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>




### <a name="periodscore--int"></a><span data-ttu-id="c171a-109">periodScore: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c171a-109">periodScore : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c171a-110">A pontozási pontok közötti átmenet lépéseinek száma.</span><span class="sxs-lookup"><span data-stu-id="c171a-110">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="c171a-111">A legjobb pontosság érdekében állítsa az 1 értékre.</span><span class="sxs-lookup"><span data-stu-id="c171a-111">For best accuracy, set to 1.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="c171a-112">beállítások: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="c171a-112">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="c171a-113">A képzésben használandó beállítások.</span><span class="sxs-lookup"><span data-stu-id="c171a-113">Options to be used in training.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="c171a-114">modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="c171a-114">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="c171a-115">A képezni kívánt szekvenciális modell.</span><span class="sxs-lookup"><span data-stu-id="c171a-115">The sequential model to be trained.</span></span>


### <a name="npreviousbestmisses--int"></a><span data-ttu-id="c171a-116">nPreviousBestMisses: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c171a-116">nPreviousBestMisses : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c171a-117">A korábbi korszakokban megfigyelt téves besorolások legjobb száma.</span><span class="sxs-lookup"><span data-stu-id="c171a-117">The best number of misclassifications observed in previous epochs.</span></span>



## <a name="output--intsequentialmodel"></a><span data-ttu-id="c171a-118">Kimenet: ([int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span><span class="sxs-lookup"><span data-stu-id="c171a-118">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span></span>

- <span data-ttu-id="c171a-119">Az ezen a korszakon keresztül megfigyelt téves besorolások legkisebb száma.</span><span class="sxs-lookup"><span data-stu-id="c171a-119">The smallest number of misclassifications observed through to this epoch.</span></span>
- <span data-ttu-id="c171a-120">A rendszer az új, legjobb szekvenciális modellt találta.</span><span class="sxs-lookup"><span data-stu-id="c171a-120">The new best sequential model found.</span></span>