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
# <a name="_runsingletrainingepoch-operation"></a>_RunSingleTrainingEpoch művelet

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


Hajtson végre egy időpontot szekvenciális osztályozó képzésen az adatmintaok egy részhalmazán.

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a>Bevitel

### <a name="encodedsamples--labeledsamplestategenerator"></a>encodedSamples: ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []




### <a name="schedule--samplingschedule"></a>Schedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)




### <a name="periodscore--int"></a>periodScore: [int](xref:microsoft.quantum.lang-ref.int)

A pontozási pontok közötti átmenet lépéseinek száma.
A legjobb pontosság érdekében állítsa az 1 értékre.


### <a name="options--trainingoptions"></a>beállítások: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

A képzésben használandó beállítások.


### <a name="model--sequentialmodel"></a>modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

A képezni kívánt szekvenciális modell.


### <a name="npreviousbestmisses--int"></a>nPreviousBestMisses: [int](xref:microsoft.quantum.lang-ref.int)

A korábbi korszakokban megfigyelt téves besorolások legjobb száma.



## <a name="output--intsequentialmodel"></a>Kimenet: ([int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))

- Az ezen a korszakon keresztül megfigyelt téves besorolások legkisebb száma.
- A rendszer az új, legjobb szekvenciális modellt találta.