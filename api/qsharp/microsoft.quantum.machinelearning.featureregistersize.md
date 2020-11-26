---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196412"
---
# <a name="featureregistersize-function"></a>FeatureRegisterSize függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


Egy adott szolgáltatás vektorának kódolásához szükséges qubits számát adja vissza.

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>Bevitel

### <a name="sample--double"></a>minta: [Double](xref:microsoft.quantum.lang-ref.double)[]

Egy qubit-regiszterbe kódolható minta-szolgáltatás vektora.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

A qubit-regiszterbe való kódoláshoz szükséges méret `sample` , a qubits számában kifejezve.