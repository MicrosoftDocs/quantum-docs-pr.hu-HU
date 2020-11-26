---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: 3fe029bd893fc4d11aaf351f7ea566256cac5a9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96194729"
---
# <a name="pnorm-function"></a>PNorm függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Az `L(p)` s vektorának normáját adja vissza `Double` .

Ez azt eredményezi, hogy egy tömb $x $ típusú `Double[]` , ez a következőt adja vissza: $p $-norm $ \| x \| \_ p = (\ sum_ {j} | x_j | ^ {p}) ^ {1/p} $.

```qsharp
function PNorm (p : Double, array : Double[]) : Double
```


## <a name="input"></a>Bevitel

### <a name="p--double"></a>p: [dupla](xref:microsoft.quantum.lang-ref.double)

A kitevő $p $ a $p $-NORM.


### <a name="array--double"></a>tömb: [Double](xref:microsoft.quantum.lang-ref.double)[]





## <a name="output--double"></a>Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)

A $p $-norm $ \| x \| _p $.