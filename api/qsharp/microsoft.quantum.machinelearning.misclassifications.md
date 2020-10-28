---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Nem kategorizált besorolási függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723584"
---
# <a name="misclassifications-function"></a>Nem kategorizált besorolási függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


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