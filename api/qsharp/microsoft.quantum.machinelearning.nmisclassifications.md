---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 30d049ba54630cd2f5f350280bad7f587599f459
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196310"
---
# <a name="nmisclassifications-function"></a>NMisclassifications függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


A kikövetkeztetett címkék és a megfelelő címkék egy halmaza adott számú indexet ad vissza, amelyekben az egyes címkék eltérőek.

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>Bevitel

### <a name="proposed--int"></a>javasolt: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>tényleges: [int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Az indexek száma `idx` `inferredLabels[idx] != actualLabels[idx]` .