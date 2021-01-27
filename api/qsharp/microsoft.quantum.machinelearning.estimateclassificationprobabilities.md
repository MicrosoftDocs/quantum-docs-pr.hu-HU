---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: EstimateClassificationProbabilities művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: eea503d042d6ffc241186c117a7c02ee72983b09
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847719"
---
# <a name="estimateclassificationprobabilities-operation"></a>EstimateClassificationProbabilities művelet

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Egy minta és egy szekvenciális osztályozó alapján a minták besorolási valószínűségét az egyes mintákon az osztályozó kimenetének ismételt mérésével becsüli meg.

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a>Bevitel

### <a name="tolerance--double"></a>tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)

Az a tűréshatár, amely lehetővé teszi a minta kódolását az állapot-előkészítési műveletben.


### <a name="model--sequentialmodel"></a>modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Az adott minták besorolási valószínűségének becslésére szolgáló szekvenciális modell.


### <a name="samples--double"></a>minták: [Double](xref:microsoft.quantum.lang-ref.double)[] []

A besorolni kívánt mintákhoz tartozó szolgáltatás-vektorok tömbje.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

A besorolási valószínűség becslése során használandó mérések száma.



## <a name="output--double"></a>Kimenet: [Double](xref:microsoft.quantum.lang-ref.double)[]

Az egyes minták besorolási valószínűségére vonatkozó becslések egy tömbje.