---
uid: Microsoft.Quantum.Math.PNorm
title: PNorm függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: PNorm
qsharp.summary: >-
  Returns the `L(p)` norm of a vector of `Double`s.

  That is, given an array $x$ of type `Double[]`, this returns the $p$-norm $\|x\|\_p= (\sum_{j}|x_j|^{p})^{1/p}$.
ms.openlocfilehash: cea85715e448305486f6d8a6c10e11da56edf3ee
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722297"
---
# <a name="pnorm-function"></a>PNorm függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


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