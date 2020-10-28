---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: ValidateSequentialClassifier művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: 802f1045ea4086bd371d68018a481182cb75b209
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720448"
---
# <a name="validatesequentialclassifier-operation"></a><span data-ttu-id="79347-102">ValidateSequentialClassifier művelet</span><span class="sxs-lookup"><span data-stu-id="79347-102">ValidateSequentialClassifier operation</span></span>

<span data-ttu-id="79347-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="79347-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="79347-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="79347-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="79347-105">Egy adott szekvenciális besorolást érvényesít az előre jelzett minták adott készletén.</span><span class="sxs-lookup"><span data-stu-id="79347-105">Validates a given sequential classifier against a given set of pre-labeled samples.</span></span>

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a><span data-ttu-id="79347-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="79347-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="79347-107">modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="79347-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="79347-108">Az ellenőrizni kívánt szekvenciális modell.</span><span class="sxs-lookup"><span data-stu-id="79347-108">The sequential model to be validated.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="79347-109">minták: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="79347-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="79347-110">Az adott modell érvényesítéséhez használandó minták.</span><span class="sxs-lookup"><span data-stu-id="79347-110">The samples to be used to validate the given model.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="79347-111">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="79347-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="79347-112">Az egyes mintáknak a szekvenciális osztályozó bemenetként való kódolásakor használandó közelítési tűréshatár.</span><span class="sxs-lookup"><span data-stu-id="79347-112">The approximation tolerance to use in encoding each sample as an input to the sequential classifier.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="79347-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="79347-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="79347-114">Az egyes minták besorolásakor használandó mérések száma.</span><span class="sxs-lookup"><span data-stu-id="79347-114">The number of measurements to use in classifying each sample.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="79347-115">validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="79347-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="79347-116">Az az ütemterv, amellyel a mintákat az ellenőrzési készletből kell kirajzolni.</span><span class="sxs-lookup"><span data-stu-id="79347-116">The schedule by which samples should be drawn from the validation set.</span></span>



## <a name="output--validationresults"></a><span data-ttu-id="79347-117">Kimenet: [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span><span class="sxs-lookup"><span data-stu-id="79347-117">Output : [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span></span>

<span data-ttu-id="79347-118">A megadott ellenőrzés eredményei.</span><span class="sxs-lookup"><span data-stu-id="79347-118">The results of the given validation.</span></span>