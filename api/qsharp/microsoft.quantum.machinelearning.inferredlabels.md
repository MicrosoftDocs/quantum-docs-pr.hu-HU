---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 576b4b1f11fc21476bbb019d4b0326981294528c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848395"
---
# <a name="inferredlabels-function"></a>InferredLabels függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


A besorolási valószínűségek és a torzítások tömbje az egyes valószínűségek alapján kikövetkeztetett címkét adja vissza.

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a>Bevitel

### <a name="bias--double"></a>torzítás: [dupla](xref:microsoft.quantum.lang-ref.double)

A két osztály közötti torzítás, jellemzően az osztályozó betanításának eredménye.


### <a name="probabilities--double"></a>valószínűségek: [Double](xref:microsoft.quantum.lang-ref.double)[]

Több minta besorolási valószínűségének tömbje, amely jellemzően a besorolási gyakoriságok becslését eredményezi.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]

Az egyes besorolási valószínűségtől kikövetkeztetett címke.