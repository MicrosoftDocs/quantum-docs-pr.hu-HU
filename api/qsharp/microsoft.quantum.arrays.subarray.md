---
uid: Microsoft.Quantum.Arrays.Subarray
title: Tömb függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: be7b6ee1a396d67ebc311d8d97f4bd751a32d171
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718841"
---
# <a name="subarray-function"></a>Tömb függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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