---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: ExtendedGreatestCommonDivisorL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: e671405045d6d2587a8c6ccbac4ae3402f92f722
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723711"
---
# <a name="extendedgreatestcommondivisorl-function"></a>ExtendedGreatestCommonDivisorL függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


Kiszámítja az $ (u, v) $ értéket, hogy $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $, ahol a $ \operatorname{GCD} $ $a $ Greatest Common osztója $a $ és $b $. A GCD mindig pozitív.

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a>Bevitel

### <a name="a--bigint"></a>a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

az első szám, amelynek kiterjesztett legnagyobb közös osztójának kiszámítása folyamatban van


### <a name="b--bigint"></a>b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

a második szám, amelynek kiterjesztett legnagyobb közös osztója kiszámítva



## <a name="output--bigintbigint"></a>Kimenet: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))

Rekord $ (u, v) $, $u \cdot a + v \cdot b = \operatorname{GCD} (a, b) $ tulajdonsággal.

## <a name="references"></a>Referencia

- Ez a megvalósítás a következő szerint https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm