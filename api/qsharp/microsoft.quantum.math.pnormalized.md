---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: 6f9dfebe83f52cbf486cd8e6874d3699f5e6b8ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722283"
---
# <a name="pnormalized-function"></a>PNormalized függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


Normalizálja `Double` az s-vektort a `L(p)` normában.

Ez azt eredményezi, hogy egy Array $x $ típusú tömbben `Double[]` olyan tömböt ad vissza, amelyben az összes elem a $p $-norm $ \| x _p $ értékkel van elosztva \| .

```qsharp
function PNormalized (p : Double, array : Double[]) : Double[]
```


## <a name="input"></a>Bevitel

### <a name="p--double"></a>p: [dupla](xref:microsoft.quantum.lang-ref.double)

A kitevő $p $ a $p $-NORM.


### <a name="array--double"></a>tömb: [Double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Kimenet: [Double](xref:microsoft.quantum.lang-ref.double)[]

A $p $-norm $ \| x _p $ $x által normalizált tömb \| .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Math. PNorm](xref:Microsoft.Quantum.Math.PNorm)