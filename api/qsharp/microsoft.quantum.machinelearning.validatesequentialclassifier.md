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
# <a name="validatesequentialclassifier-operation"></a>ValidateSequentialClassifier művelet

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


Egy adott szekvenciális besorolást érvényesít az előre jelzett minták adott készletén.

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a>Bevitel

### <a name="model--sequentialmodel"></a>modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Az ellenőrizni kívánt szekvenciális modell.


### <a name="samples--labeledsample"></a>minták: [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

Az adott modell érvényesítéséhez használandó minták.


### <a name="tolerance--double"></a>tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)

Az egyes mintáknak a szekvenciális osztályozó bemenetként való kódolásakor használandó közelítési tűréshatár.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

Az egyes minták besorolásakor használandó mérések száma.


### <a name="validationschedule--samplingschedule"></a>validationSchedule: [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

Az az ütemterv, amellyel a mintákat az ellenőrzési készletből kell kirajzolni.



## <a name="output--validationresults"></a>Kimenet: [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)

A megadott ellenőrzés eredményei.