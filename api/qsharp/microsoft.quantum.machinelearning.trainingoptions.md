---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: TrainingOptions-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 5ecc2b5175a4e8db78f72311ac1d5ff964bae811
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722380"
---
# <a name="trainingoptions-user-defined-type"></a>TrainingOptions-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


A kvantum-osztályozók betanításakor használandó lehetőségek gyűjteménye.

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="learningrate--double"></a>LearningRate: [dupla](xref:microsoft.quantum.lang-ref.double)

Az a képzési arány, amellyel a színátmeneteket át kell méretezni a modell paramétereinek a betanítási lépések során történő frissítésekor.
### <a name="tolerance--double"></a>Tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)

A minták Quantum állapotként való előkészítésekor használandó közelítési tolerancia.
### <a name="minibatchsize--int"></a>MinibatchSize: [int](xref:microsoft.quantum.lang-ref.int)

Az egyes betanítási minibatch használandó minták száma.
### <a name="nmeasurements--int"></a>NMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

A besorolási valószínűség kiszámításához az egyes besorolások mérési eredményeinek száma.
### <a name="maxepochs--int"></a>MaxEpochs: [int](xref:microsoft.quantum.lang-ref.int)

Az egyes modellek betanításához szükséges időkorszakok maximális száma.
### <a name="maxstalls--int"></a>MaxStalls: [int](xref:microsoft.quantum.lang-ref.int)

A betanítási időpontok maximális száma (körülbelül nulla átmenet) a sikertelenség előtt.
### <a name="stochasticrescalefactor--double"></a>StochasticRescaleFactor: [dupla](xref:microsoft.quantum.lang-ref.double)

Az elakadt modellek újraméretezésének mértéke a frissítés újbóli megkísérlése előtt.
### <a name="scoringperiod--int"></a>ScoringPeriod: [int](xref:microsoft.quantum.lang-ref.int)

A pontozási pontok közötti átmenet lépéseinek száma.
A legjobb pontosság érdekében állítsa az 1 értékre.
### <a name="verbosemessage--string---unit"></a>VerboseMessage: [sztring](xref:microsoft.quantum.lang-ref.string) -> [egység](xref:microsoft.quantum.lang-ref.unit)

A részletes visszajelzések biztosítására használható függvény.

## <a name="remarks"></a>Megjegyzések

Ez a UDT nem hozható létre közvetlenül, hanem meg kell adni a meghívásával, @"microsoft.quantum.machinelearning.defaulttrainingoptions" majd az `w/` operátor használatával a különböző alapértelmezett értékek felülbírálására.

Például az 100 000 mérések és a legfeljebb 8 képzési időszak használata esetén:

```Q#
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a>Referencia

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)