---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 9e356d68233519978e007e5a2999ca1be8cb7f83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709735"
---
# <a name="nmisclassifications-function"></a>NMisclassifications függvény

Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Csomag [](https://nuget.org/packages/)


A kikövetkeztetett címkék és a megfelelő címkék egy halmaza adott számú indexet ad vissza, amelyekben az egyes címkék eltérőek.

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>Bevitel

### <a name="proposed--int"></a>javasolt: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>tényleges: [int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

Az indexek száma `idx` `inferredLabels[idx] != actualLabels[idx]` .