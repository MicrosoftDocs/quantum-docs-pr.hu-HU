---
uid: Microsoft.Quantum.Arrays.Transposed
title: Átültetett függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: f293399d8e3a2cb32b2929e8d1591ac5eaefd277
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219991"
---
# <a name="transposed-function"></a>Átültetett függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tömbök tömbje jelölt mátrix átültetését adja vissza.

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a>Leírás

Bemenet $r \times c $ mátrixként $r $ sorokkal és $c $ oszlopokkal.  A mátrix egy sor-alapú, azaz a `matrix[i][j]` (z) $i $ és a $j $ oszlopban lévő elemhez fér hozzá.

Ez a függvény a bemeneti mátrix átültetésének $c \times r $ mátrixot adja vissza.

## <a name="input"></a>Bevitel

### <a name="matrix--t"></a>mátrix: 'T [] []

Sor-alapú $r \times c $ mátrix



## <a name="output--t"></a>Kimenet: 'T [] []

Átültetett $c \times r $ Matrix

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az egyes elemeinek típusa `matrix` .