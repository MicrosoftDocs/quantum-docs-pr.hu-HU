---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: DefaultTrainingOptions függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855994"
---
# <a name="defaulttrainingoptions-function"></a>DefaultTrainingOptions függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Az osztályozók betanítási beállításainak alapértelmezett készletét adja vissza.

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a>Kimenet: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

Az osztályozók betanításakor használható alapértelmezett képzési lehetőségek ésszerű készlete.

## <a name="example"></a>Példa

Az alapértelmezett beállítások használatához, de további mérések esetén használja az `w/` operátort:

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```