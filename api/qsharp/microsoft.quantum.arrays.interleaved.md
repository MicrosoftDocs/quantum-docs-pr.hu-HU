---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Interleaved függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848116"
---
# <a name="interleaved-function"></a>Interleaved függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Két tömb (majdnem) egyazon méretének együttes elhagyása.

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a>Leírás

Ez a függvény két tömb összekapcsolását adja vissza, kezdve az első tömb első elemével, a második tömb első elemével és így tovább.

Az első tömbnek ugyanolyan hosszúságú kell lennie, mint a másodiknak, vagy rendelkezhet még egy elemmel.

## <a name="input"></a>Bevitel

### <a name="first--t"></a>első: 'T []

Az első elhagyni kívánt tömb.


### <a name="second--t"></a>második: 'T []

Az összekapcsolni kívánt második tömb.



## <a name="output--t"></a>Kimenet: 'T []

Átfedésben lévő tömb

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A és a egyes elemeinek `first` típusa `second` .

## <a name="example"></a>Példa

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```