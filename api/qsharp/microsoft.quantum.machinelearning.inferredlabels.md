---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 874d1a2f7cc6d67567e0d2baa70b0d26b639a029
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722479"
---
# <a name="inferredlabels-function"></a>InferredLabels függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


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