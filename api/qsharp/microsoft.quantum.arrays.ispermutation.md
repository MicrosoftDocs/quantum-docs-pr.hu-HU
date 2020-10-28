---
uid: Microsoft.Quantum.Arrays.IsPermutation
title: IsPermutation függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsPermutation
qsharp.summary: Outputs true if and only if a given array represents a permutation.
ms.openlocfilehash: 361bb21bedc725c25a1f3dfc811e9cfda4cb45ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719105"
---
# <a name="ispermutation-function"></a>IsPermutation függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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



## <a name="remarks"></a>Megjegyzések

A nulla hosszúságú tömb triviálisan egy permutáció.