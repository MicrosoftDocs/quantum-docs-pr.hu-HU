---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 8cb21ae5052ae6c5a8aed8be71d6bd3d32034272
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723724"
---
# <a name="extendedgreatestcommondivisori-function"></a>ExtendedGreatestCommonDivisorI függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


Kiszámítja az $ (u, v) $ értéket, hogy $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, ahol a $ \operatorname{GCD} $ $a $ Greatest Common osztója $a $ és $b $. A GCD mindig pozitív.

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a>Bevitel

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

az első szám, amelynek kiterjesztett legnagyobb közös osztójának kiszámítása folyamatban van


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

a második szám, amelynek kiterjesztett legnagyobb közös osztója kiszámítva



## <a name="output--intint"></a>Kimenet: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))

Rekord $ (u, v) $, $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $ tulajdonsággal.

## <a name="references"></a>Referencia

- Ez a megvalósítás a következő szerint https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm