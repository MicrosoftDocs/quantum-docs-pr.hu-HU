---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 2c110f9abf18ee81bd72a68601d5c41ff756290a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851352"
---
# <a name="iscoprimei-function"></a>IsCoprimeI függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Igaz értéket ad vissza, ha a $a $ és a $b $ együttes elsődleges és hamis.

```qsharp
function IsCoprimeI (a : Int, b : Int) : Bool
```


## <a name="input"></a>Bevitel

### <a name="a--int"></a>a: [int](xref:microsoft.quantum.lang-ref.int)

az első szám, amelynek a közös primality tesztelése folyamatban van


### <a name="b--int"></a>b: [int](xref:microsoft.quantum.lang-ref.int)

a második szám, amelynek a közös primality tesztelve van



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

Igaz, ha a $a $ és a $b $ együttes elsődleges (például a legnagyobb közös osztó értéke 1), máskülönben hamis értéket ad meg.