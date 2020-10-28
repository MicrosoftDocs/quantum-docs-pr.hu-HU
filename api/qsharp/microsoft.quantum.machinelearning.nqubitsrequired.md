---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: d7ed687e9c75ed7cc71917aa1cdf32a6fbb93106
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723571"
---
# <a name="nqubitsrequired-function"></a>NQubitsRequired függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


Egy adott szekvenciális osztályozó alkalmazásához szükséges qubits számát adja vissza.

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a>Bevitel

### <a name="model--sequentialmodel"></a>modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)





## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Azon regiszter minimális mérete, amelyen a szekvenciális osztályozó alkalmazható.