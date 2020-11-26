---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Nem kategorizált besorolási függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: e13a9b9b65931678d5d87878e81fa172329a28ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211678"
---
# <a name="misclassifications-function"></a>Nem kategorizált besorolási függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


A kikövetkeztetett címkék és a megfelelő címkék halmaza miatt a rendszer az indexeket adja vissza, amelyekben az egyes címkék eltérőek.

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a>Bevitel

### <a name="inferredlabels--int"></a>inferredLabels: [int](xref:microsoft.quantum.lang-ref.int)[]

Egy adott képzésre vagy érvényesítési csoportra hivatkozó címkék.


### <a name="actuallabels--int"></a>actualLabels: [int](xref:microsoft.quantum.lang-ref.int)[]

Egy adott képzés vagy érvényesítési csoport valódi címkéi.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]

Olyan indexek tömbje `idx` , amelyek ilyenek `inferredLabels[idx] != actualLabels[idx]` .