---
uid: Microsoft.Quantum.Math.PNormalized
title: PNormalized függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNormalized
qsharp.summary: >-
  Normalizes a vector of `Double`s in the `L(p)` norm.

  That is, given an array $x$ of type `Double[]`, this returns an array where all elements are divided by the $p$-norm $\|x\|_p$.
ms.openlocfilehash: ea6a88d07d3b246f666b793f0b10ab6598ea4ff6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854847"
---
# <a name="pnormalized-function"></a>PNormalized függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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