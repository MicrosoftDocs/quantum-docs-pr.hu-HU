---
uid: Microsoft.Quantum.Arrays.Transposed
title: Átültetett függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 913f1829ef53ec3eb6944be8b8e3eb37b431f27e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850932"
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

## <a name="example"></a>Példa

```qsharp
// same as [[1, 4], [2, 5], [3, 6]]
let transposed = Transposed([[1, 2, 3], [4, 5, 6]]);
```