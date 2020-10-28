---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: 7c077d508c93672d58a52a1403b3c5d73df75471
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722310"
---
# <a name="iscoprimel-function"></a>IsCoprimeL függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag [](https://nuget.org/packages/)


Igaz értéket ad vissza, ha a $a $ és a $b $ együttes elsődleges és hamis.

```qsharp
function IsCoprimeL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a>Bevitel

### <a name="a--bigint"></a>a: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

az első szám, amelynek a közös primality tesztelése folyamatban van


### <a name="b--bigint"></a>b: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

a második szám, amelynek a közös primality tesztelve van



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

Igaz, ha a $a $ és a $b $ együttes elsődleges (például a legnagyobb közös osztó értéke 1), máskülönben hamis értéket ad meg.