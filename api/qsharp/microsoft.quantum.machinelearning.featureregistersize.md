---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 8f7c47c7547e7a0ac1672f308de445c1b46461e1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723290"
---
# <a name="featureregistersize-function"></a>FeatureRegisterSize függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


Egy adott szolgáltatás vektorának kódolásához szükséges qubits számát adja vissza.

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a>Bevitel

### <a name="sample--double"></a>minta: [Double](xref:microsoft.quantum.lang-ref.double)[]

Egy qubit-regiszterbe kódolható minta-szolgáltatás vektora.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

A qubit-regiszterbe való kódoláshoz szükséges méret `sample` , a qubits számában kifejezve.