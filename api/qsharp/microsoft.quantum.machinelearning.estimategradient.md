---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 38edcb67e7dcc5d2e971fb507a792937774a702c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844385"
---
# <a name="estimategradient-operation"></a>EstimateGradient művelet

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Egy adott modellen belül egy szekvenciális osztályozó, egy adott kódolt bemenet esetében pedig a betanítási átmenetet becsüli meg.

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a>Bevitel

### <a name="model--sequentialmodel"></a>modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

Az a szekvenciális modell, amelynek gradiensét meg kell becsülni.


### <a name="encodedinput--stategenerator"></a>encodedInput: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

A szekvenciális osztályozó bemenete, amely egy állapot-előkészítési műveletbe van kódolva.


### <a name="nmeasurements--int"></a>nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)

A színátmenet becsléséhez használni kívánt mérések száma.



## <a name="output--double"></a>Kimenet: [Double](xref:microsoft.quantum.lang-ref.double)[]

A betanítási és a modell paramétereinek a betanítási átmenetének becslése.

## <a name="remarks"></a>Megjegyzések

Ez a művelet egy Hadamard tesztet és a paraméter-eltolási technikát használja együtt a színátmenet becsléséhez.