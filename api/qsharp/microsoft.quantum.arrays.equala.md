---
uid: Microsoft.Quantum.Arrays.EqualA
title: Equala függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 24fd76aaeb66081d6d8f1eaa3056117f54b5a5e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719285"
---
# <a name="equala-function"></a>Equala függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


Adott típusú két tömb, valamint egy, a tömbök elemeihez definiált predikátum is ellenőrzi, hogy a tömbök egyenlőek-e.

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a>Bevitel

### <a name="equal--tt---bool"></a>egyenlő: (nem, 'T) – > [bool](xref:microsoft.quantum.lang-ref.bool)

A rekordból egy függvény, amely azt vizsgálja, hogy a `('T, 'T)` `Bool` tömbök két eleme egyenlő-e.


### <a name="array1--t"></a>tömb1: nem []

Az elsőként összehasonlítható tömb.


### <a name="array2--t"></a>tömb2: nem []

Az összehasonlítandó második tömb.



## <a name="output--bool"></a>Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)

Az érték `true` , ha és csak akkor, ha `array1` és `array2` egyenlő.
Vagyis ha mindkét tömb azonos hosszúságú, és az összes elem megegyezik a által meghatározott értékkel `equal` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az egyes tömbök elemeinek típusa.

## <a name="remarks"></a>Megjegyzések

Ez a függvény általános típusokhoz van definiálva; azaz, ha két tömb `'T[]` és egy függvény van `equal: ('T, 'T) -> Bool` , akkor ez a függvény egy értéket ad vissza, `Bool` amely jelzi, hogy a tömbök egyenlőek-e.
Ha két tömbnek egyenlőnek kell lennie, akkor egyenlőnek kell lennie, és a tömbök azonos helyein lévő elemeknek egyenlőnek kell lenniük.