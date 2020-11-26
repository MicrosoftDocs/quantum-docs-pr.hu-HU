---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: TrainingOptions-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 280a3857aa7bc42f636a33f893d4f450e79b6a6a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196123"
---
# <a name="trainingoptions-user-defined-type"></a><span data-ttu-id="7ae13-102">TrainingOptions-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="7ae13-102">TrainingOptions user defined type</span></span>

<span data-ttu-id="7ae13-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7ae13-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="7ae13-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="7ae13-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="7ae13-105">A kvantum-osztályozók betanításakor használandó lehetőségek gyűjteménye.</span><span class="sxs-lookup"><span data-stu-id="7ae13-105">A collection of options to be used in training quantum classifiers.</span></span>

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a><span data-ttu-id="7ae13-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="7ae13-106">Named Items</span></span>

### <a name="learningrate--double"></a><span data-ttu-id="7ae13-107">LearningRate: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7ae13-107">LearningRate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7ae13-108">Az a képzési arány, amellyel a színátmeneteket át kell méretezni a modell paramétereinek a betanítási lépések során történő frissítésekor.</span><span class="sxs-lookup"><span data-stu-id="7ae13-108">The learning rate by which gradients should be rescaled when updating model parameters during training steps.</span></span>
### <a name="tolerance--double"></a><span data-ttu-id="7ae13-109">Tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7ae13-109">Tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7ae13-110">A minták Quantum állapotként való előkészítésekor használandó közelítési tolerancia.</span><span class="sxs-lookup"><span data-stu-id="7ae13-110">The approximation tolerance to use when preparing samples as quantum states.</span></span>
### <a name="minibatchsize--int"></a><span data-ttu-id="7ae13-111">MinibatchSize: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7ae13-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7ae13-112">Az egyes betanítási minibatch használandó minták száma.</span><span class="sxs-lookup"><span data-stu-id="7ae13-112">The number of samples to use in each training minibatch.</span></span>
### <a name="nmeasurements--int"></a><span data-ttu-id="7ae13-113">NMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7ae13-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7ae13-114">A besorolási valószínűség kiszámításához az egyes besorolások mérési eredményeinek száma.</span><span class="sxs-lookup"><span data-stu-id="7ae13-114">The number of times to measure each classification result in order to estimate the classification probability.</span></span>
### <a name="maxepochs--int"></a><span data-ttu-id="7ae13-115">MaxEpochs: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7ae13-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7ae13-116">Az egyes modellek betanításához szükséges időkorszakok maximális száma.</span><span class="sxs-lookup"><span data-stu-id="7ae13-116">The maximum number of epochs to train each model for.</span></span>
### <a name="maxstalls--int"></a><span data-ttu-id="7ae13-117">MaxStalls: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7ae13-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7ae13-118">A betanítási időpontok maximális száma (körülbelül nulla átmenet) a sikertelenség előtt.</span><span class="sxs-lookup"><span data-stu-id="7ae13-118">The maximum number of times a training epoch is allowed to stall (approximately zero gradient) before failing.</span></span>
### <a name="stochasticrescalefactor--double"></a><span data-ttu-id="7ae13-119">StochasticRescaleFactor: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7ae13-119">StochasticRescaleFactor : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7ae13-120">Az elakadt modellek újraméretezésének mértéke a frissítés újbóli megkísérlése előtt.</span><span class="sxs-lookup"><span data-stu-id="7ae13-120">The amount to rescale stalled models by before retrying an update.</span></span>
### <a name="scoringperiod--int"></a><span data-ttu-id="7ae13-121">ScoringPeriod: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7ae13-121">ScoringPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7ae13-122">A pontozási pontok közötti átmenet lépéseinek száma.</span><span class="sxs-lookup"><span data-stu-id="7ae13-122">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="7ae13-123">A legjobb pontosság érdekében állítsa az 1 értékre.</span><span class="sxs-lookup"><span data-stu-id="7ae13-123">For best accuracy, set to 1.</span></span>
### <a name="verbosemessage--string---unit"></a><span data-ttu-id="7ae13-124">VerboseMessage: [sztring](xref:microsoft.quantum.lang-ref.string) -> [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7ae13-124">VerboseMessage : [String](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="7ae13-125">A részletes visszajelzések biztosítására használható függvény.</span><span class="sxs-lookup"><span data-stu-id="7ae13-125">A function that can be used to provide verbose feedback.</span></span>

## <a name="remarks"></a><span data-ttu-id="7ae13-126">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="7ae13-126">Remarks</span></span>

<span data-ttu-id="7ae13-127">Ez a UDT nem hozható létre közvetlenül, hanem meg kell adni a meghívásával, @"microsoft.quantum.machinelearning.defaulttrainingoptions" majd az `w/` operátor használatával a különböző alapértelmezett értékek felülbírálására.</span><span class="sxs-lookup"><span data-stu-id="7ae13-127">This UDT should not be created directly, but rather should be specified by calling @"microsoft.quantum.machinelearning.defaulttrainingoptions" and then using the `w/` operator to override different defaults.</span></span>

<span data-ttu-id="7ae13-128">Például az 100 000 mérések és a legfeljebb 8 képzési időszak használata esetén:</span><span class="sxs-lookup"><span data-stu-id="7ae13-128">For example, to use 100,000 measurements and at most 8 training epochs:</span></span>

```Q#
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a><span data-ttu-id="7ae13-129">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="7ae13-129">References</span></span>

- [<span data-ttu-id="7ae13-130">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="7ae13-130">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)