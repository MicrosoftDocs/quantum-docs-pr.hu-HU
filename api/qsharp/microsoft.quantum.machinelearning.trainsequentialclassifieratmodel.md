---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel
title: TrainSequentialClassifierAtModel művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifierAtModel
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.
ms.openlocfilehash: 02a300a2e1029d0e09aba19d090e15128fede717
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211463"
---
# <a name="trainsequentialclassifieratmodel-operation"></a>TrainSequentialClassifierAtModel művelet

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Egy szekvenciális osztályozó szerkezete miatt az osztályozó egy adott megcímkézett betanítási készleten, egy adott modelltől indul.

```qsharp
operation TrainSequentialClassifierAtModel (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a>Bevitel

### <a name="model--sequentialmodel"></a>modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

A betanítás kiindulási pontként használandó szekvenciális modell.


### <a name="samples--labeledsample"></a>minták: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

A kiképzések elvégzéséhez használt címkézett betanítási adatok halmaza.


### <a name="options--trainingoptions"></a>beállítások: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

A Betanításkor használandó konfiguráció @"microsoft.quantum.machinelearning.trainingoptions" @"microsoft.quantum.machinelearning.defaulttrainingoptions" További részletekért lásd: és.


### <a name="trainingschedule--samplingschedule"></a>trainingSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Mintavételezési ütemterv, amely a betanítási adatokban a minták kiválasztásakor használatos a betanítási lépések során.


### <a name="validationschedule--samplingschedule"></a>validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

A betanítási adatok mintáinak kiválasztásakor használandó mintavételi ütemterv, amikor kiválasztja, hogy melyik kezdőpont eredményezte a legjobb osztályozó pontszámot.



## <a name="output--sequentialmodelint"></a>Kimenet: ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[int](xref:microsoft.quantum.lang-ref.int))

- A megadott osztályozó paraméterezés és a két osztály közötti torzítás, valamint az egyes megadott kezdőpontok legjobb eredményének megfelelő.
- A legjobb osztályozó modellben megfigyelt hiányoznak száma.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. MachineLearning. TrainSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifier)
- [Microsoft. Quantum. MachineLearning. ValidateSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)