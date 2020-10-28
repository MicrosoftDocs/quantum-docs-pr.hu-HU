---
uid: Microsoft.Quantum.Arrays.Transposed
title: Átültetett függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718816"
---
# <a name="transposed-function"></a>Átültetett függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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