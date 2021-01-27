---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 7e563650f33b0292e1e41f629829a2d3b9e5fd28
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848098"
---
# <a name="ispermutation-function"></a>IsPermutation függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Igaz értéket ad eredményül, ha a megadott tömb egy permutációt jelöl.

```qsharp
function IsPermutation (permuation : Int[]) : Bool
```


## <a name="description"></a>Leírás

A `array` Hossz `n` függvényében az igaz értéket adja vissza, és csak akkor, ha a és a közötti egész szám `0` `n - 1` pontosan egyszer jelenik meg a (z)-ben `array` , így az `array` elemek esetében permutációként is értelmezhető `n` .

## <a name="input"></a>Bevitel

### <a name="permuation--int"></a>permuation: [int](xref:microsoft.quantum.lang-ref.int)[]

Egy olyan tömb, amely lehet, hogy nem egy permutációt jelöl.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)



## <a name="example"></a>Példa

A következő Q # kód kinyomtatja az "összes diagnosztika sikeresen befejeződött" üzenetet:

```qsharp
Fact(IsPermutation([2, 0, 1], "");
Contradiction(IsPermutation([5, 0, 1], "[5, 0, 1] isn't a permutation");
Message("All diagnostics completed successfully.");
```

## <a name="remarks"></a>Megjegyzések

A nulla hosszúságú tömb triviálisan egy permutáció.