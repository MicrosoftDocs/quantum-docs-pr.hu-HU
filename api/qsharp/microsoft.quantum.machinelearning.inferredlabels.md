---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 668ab89ed45c49d33ce50ff5d892f4d57246c12a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196361"
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