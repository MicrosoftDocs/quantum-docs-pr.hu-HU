---
uid: Microsoft.Quantum.Math.IsCoprimeL
title: IsCoprimeL függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: IsCoprimeL
qsharp.summary: Returns true if $a$ and $b$ are co-prime and false otherwise.
ms.openlocfilehash: a48f056d138499607d32b38b1fa0970745732c41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851345"
---
# <a name="iscoprimel-function"></a>IsCoprimeL függvény

Névtér: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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