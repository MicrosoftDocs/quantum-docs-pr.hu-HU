---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Átlós függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719381"
---
# <a name="diagonal-function"></a>Átlós függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


Egy kétdimenziós tömb átlós elemeinek tömbjét adja vissza.

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>Leírás

Ha a 2 dimenziós tömb nem rendelkezik négyzet alakú alakzattal, akkor a rendszer a sorok és oszlopok számának legkisebb feletti átlóját adja vissza.

## <a name="input"></a>Bevitel

### <a name="matrix--t"></a>mátrix: 'T [] []

2 dimenziós mátrix a Row-Wise sorrendben



## <a name="output--t"></a>Kimenet: 'T []



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az egyes elemeinek típusa `matrix` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Arrays. átültetve](xref:Microsoft.Quantum.Arrays.Transposed)