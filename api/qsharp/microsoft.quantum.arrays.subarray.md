---
uid: Microsoft.Quantum.Arrays.Subarray
title: Tömb függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: cf72f04421b277ce64354d1eccec11cbc61d78cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220161"
---
# <a name="subarray-function"></a>Tömb függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy tömböt és egy listát hoz létre, és létrehoz egy új tömböt az eredeti tömb elemeiből, amelyek megfelelnek az adott helyeknek.

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Bevitel

### <a name="indices--int"></a>indexek: [int](xref:microsoft.quantum.lang-ref.int)[]

Az altömb definiálásához használt egész számok listája.


### <a name="array--t"></a>tömb: 'T []

Elemek tömbje `'T` .



## <a name="output--t"></a>Kimenet: 'T []

Olyan elemek tömbje `out` , amelyek indexei az altömbnek felelnek meg, például: `out[idx] == array[indices[idx]]` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az elemek típusa `array` .

## <a name="remarks"></a>Megjegyzések

A függvény általános típusokhoz van definiálva, azaz, ha van egy tömb, `'T[]` és `Int[]` az altömbet meghatározó helyszínek listája.
Az altömb felépítése azon alapul, hogy az adott tömb új, részletes másolatát hozza létre a hivatkozások fenntartása mellett.

Ha `Length(indices) < Length(array)` Ez a függvény a következő részhalmazát fogja visszaadni: `array` . Másfelől, ha `indices` ismétlődő elemeket tartalmaz, a megfelelő elemek is `array` megismétlődnek.
Ha `indices` `array` a és az azonos hosszúságú, akkor ez a függvény a következő funkciókat biztosítja: `array` .