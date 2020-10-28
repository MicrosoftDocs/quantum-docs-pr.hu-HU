---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Interleaved függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719141"
---
# <a name="interleaved-function"></a>Interleaved függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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