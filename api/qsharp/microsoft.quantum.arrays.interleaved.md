---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Interleaved függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220960"
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