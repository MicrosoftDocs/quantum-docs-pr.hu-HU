---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855527"
---
# <a name="decomposedon-function"></a>DecomposedOn függvény

Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Példa

Tegyük fel, hogy a bemenet a következők egyike: perm = [0, 2, 3, 5, 7, 1, 4, 6] és index = 0, ez a függvény három permutációt számít ki az alábbi táblázat alapján, amely felsorolja az a `perm` csoport és a D csoport képein belüli bináris jelölésű permutációt.  Az oszlopok felsorolják a bit indexeket.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 |       |       | 0 0 0 | 0
| 0 0 1 |       |       | 0 1 0 | 2
| 0 1 0 |       |       | 0 1 1 | 3
| 0 1 1 |       |       | 1 0 1 | 5
| 1 0 0 |       |       | 1 1 1 | 7
| 1 0 1 |       |       | 0 0 1 | 1
| 1 1 0 |       |       | 1 0 0 | 4
| 1 1 1 |       |       | 1 1 0 | 6

Az indexek összes olyan értéke, amely nem egyenlő a 0 értékkel (= index), az A-tól B-ig és D és C között lesz átmásolva.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0   | 0 0   | 0 0 0 |
| 0 0 1 | 0 0   | 0 1   | 0 1 0 |
| 0 1 0 | 0 1   | 0 1   | 0 1 1 |
| 0 1 1 | 0 1   | 1 0   | 1 0 1 |
| 1 0 0 | 1 0   | 1 1   | 1 1 1 |
| 1 0 1 | 1 0   | 0 0   | 0 0 1 |
| 1 1 0 | 1 1   | 1 0   | 1 0 0 |
| 1 1 1 | 1 1   | 1 1   | 1 1 0 |

A következő a 0 értéket helyezi el az első elemhez, amely üres indexszel rendelkezik a B blokkban található 0. oszlopban, majd egy 1 kerül a B helyére, ahol az előtag megegyezik (az első esetben a másik sor az indexekkel 0 0).
Ezt követően a rendszer egy 1 értéket ad hozzá a C blokkban található ugyanabban a sorban, majd a C blokkban található megfelelő előtaghoz a 0 értéket.  Ez a folyamat ismétlődik, amíg az összes index be nem került a 0. oszlopba a B és C tömbben.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0 0 | 0 0 0 | 0 0 0 |
| 0 0 1 | 0 0 1 | 0 1 1 | 0 1 0 |
| 0 1 0 | 0 1 0 | 0 1 0 | 0 1 1 |
| 0 1 1 | 0 1 1 | 1 0 1 | 1 0 1 |
| 1 0 0 | 1 0 0 | 1 1 0 | 1 1 1 |
| 1 0 1 | 1 0 1 | 0 0 1 | 0 0 1 |
| 1 1 0 | 1 1 0 | 1 0 0 | 1 0 0 |
| 1 1 1 | 1 1 1 | 1 1 1 | 1 1 0 |

A táblázatból három új permutációt is olvashat:

- $ \ pi_l $, a "B" kép elemeivel (bal)
- $ \ pi_r $, elemek: D, C (jobb) kép
- $ \pi ' $ a B elemekkel, C-ban található képek (hátralévő)

Vegye figyelembe, hogy a tervezési bites értékek nem változnak a $ \ pi_l $ és a $ \ pi_r $ értékben az 1. és a 2. indexek esetében, és a 0 értéknél a (z) $ \ pi_ $ értéke nem módosítható.  Azt is vegye figyelembe, hogy a $ \ pi_l $ és $ \ pi_r $ értéknek saját-inverznek kell lennie.

A származtatott és visszaadott permutációk a következők: Left = [0, 1, 2, 3, 4, 5, 6, 7] jobb = [0, 1, 3, 2, 4, 5, 7, 6] fennmaradó = [0, 3, 2, 5, 6, 1, 4, 7]