---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: f42cc30c98346a25f584d7527227a95cb413c32b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719969"
---
# <a name="estimategradient-operation"></a>EstimateGradient művelet

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


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