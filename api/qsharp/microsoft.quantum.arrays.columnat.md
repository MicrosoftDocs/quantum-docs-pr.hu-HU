---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 097b3fdd6fc1843ada27052fcf08ee80d894d25a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210098"
---
# <a name="columnat-function"></a>ColumnAt függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Oszlop kibontása egy mátrixból.

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Leírás

Ez a függvény kibontja a mátrix oszlopát a sor-Wise sorrendben.
Sorok kibontása az első index corrsponds, ezért nincs szükség további kezelésre.

## <a name="input"></a>Bevitel

### <a name="column--int"></a>oszlop: [int](xref:microsoft.quantum.lang-ref.int)

A mátrix oszlopa


### <a name="matrix--t"></a>mátrix: 'T [] []

2 dimenziós mátrix a Row-Wise sorrendben



## <a name="output--t"></a>Kimenet: 'T []



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az egyes elemeinek típusa `matrix` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Arrays. átültetve](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft. Quantum. Arrays. átló](xref:Microsoft.Quantum.Arrays.Diagonal)