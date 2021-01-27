---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846256"
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

## <a name="example"></a>Példa

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Arrays. átültetve](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft. Quantum. Arrays. átló](xref:Microsoft.Quantum.Arrays.Diagonal)