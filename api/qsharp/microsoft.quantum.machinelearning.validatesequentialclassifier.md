---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: ValidateSequentialClassifier művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: 5174085edbfd846e8f6649f33e325fd1979ae6a2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196106"
---
# <a name="validatesequentialclassifier-operation"></a><span data-ttu-id="4f3ba-102">ValidateSequentialClassifier művelet</span><span class="sxs-lookup"><span data-stu-id="4f3ba-102">ValidateSequentialClassifier operation</span></span>

<span data-ttu-id="4f3ba-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4f3ba-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="4f3ba-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4f3ba-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="4f3ba-105">Egy adott szekvenciális besorolást érvényesít az előre jelzett minták adott készletén.</span><span class="sxs-lookup"><span data-stu-id="4f3ba-105">Validates a given sequential classifier against a given set of pre-labeled samples.</span></span>

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a><span data-ttu-id="4f3ba-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4f3ba-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="4f3ba-107">modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="4f3ba-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="4f3ba-108">Az ellenőrizni kívánt szekvenciális modell.</span><span class="sxs-lookup"><span data-stu-id="4f3ba-108">The sequential model to be validated.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="4f3ba-109">minták: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="4f3ba-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="4f3ba-110">Az adott modell érvényesítéséhez használandó minták.</span><span class="sxs-lookup"><span data-stu-id="4f3ba-110">The samples to be used to validate the given model.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="4f3ba-111">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4f3ba-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4f3ba-112">Az egyes mintáknak a szekvenciális osztályozó bemenetként való kódolásakor használandó közelítési tűréshatár.</span><span class="sxs-lookup"><span data-stu-id="4f3ba-112">The approximation tolerance to use in encoding each sample as an input to the sequential classifier.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="4f3ba-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4f3ba-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4f3ba-114">Az egyes minták besorolásakor használandó mérések száma.</span><span class="sxs-lookup"><span data-stu-id="4f3ba-114">The number of measurements to use in classifying each sample.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="4f3ba-115">validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="4f3ba-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="4f3ba-116">Az az ütemterv, amellyel a mintákat az ellenőrzési készletből kell kirajzolni.</span><span class="sxs-lookup"><span data-stu-id="4f3ba-116">The schedule by which samples should be drawn from the validation set.</span></span>



## <a name="output--validationresults"></a><span data-ttu-id="4f3ba-117">Kimenet: [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span><span class="sxs-lookup"><span data-stu-id="4f3ba-117">Output : [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span></span>

<span data-ttu-id="4f3ba-118">A megadott ellenőrzés eredményei.</span><span class="sxs-lookup"><span data-stu-id="4f3ba-118">The results of the given validation.</span></span>