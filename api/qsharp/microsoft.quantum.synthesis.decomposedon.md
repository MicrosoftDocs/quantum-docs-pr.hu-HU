---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: b033723a50fb85e77c9d4baec1f94231327e9b25
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725222"
---
# <a name="decomposedon-function"></a>DecomposedOn függvény

Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)

Csomag [](https://nuget.org/packages/)


Egy változó kibontása egy változón

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>Leírás

Adott egy permutációs $ \pi $ ( `perm` ) és egy index $i $ ( `index` ), ez a módszer három permutációt ad vissza ((\ pi_l, \ pi_r), \pi ') $, hogy a $ \ pi_l $ és a $ \ pi_r $ lemezképek ne változtassák meg a BITS-t a $i $ és a $ \pi ' $ értéknél nem módosítható bit $i $ értékkel az elemekben.

## <a name="input"></a>Bevitel

### <a name="perm--int"></a>dauer: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>index: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Kimenet: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])

