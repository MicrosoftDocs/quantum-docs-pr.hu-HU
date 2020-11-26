---
uid: Microsoft.Quantum.Arrays.Diagonal
title: Átlós függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: fe6bac0acfa07b14620c7c35ae5e1cec2287d13d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221538"
---
# <a name="diagonal-function"></a>Átlós függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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