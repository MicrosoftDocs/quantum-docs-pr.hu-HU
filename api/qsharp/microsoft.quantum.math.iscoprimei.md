---
uid: Microsoft.Quantum.Math.IsCoprimeI
title: IsCoprimeI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeI
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: bdfaecb61f56967e21bf85ba190638b43685214d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723360"
---
# <a name="iscoprimei-function"></a>IsCoprimeI függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


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