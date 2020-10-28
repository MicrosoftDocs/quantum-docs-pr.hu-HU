---
uid: Microsoft.Quantum.Arrays.Unique
title: Egyedi függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: c5d40bb82f2de640e9c78eef0c27e4766b477826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718781"
---
# <a name="unique-function"></a>Egyedi függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


Egy olyan új tömböt ad vissza, amely nem tartalmaz egyenlő szomszédos elemeket.

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a>Leírás

A függvény az elemek egy tömbjét és egy olyan függvényt ad vissza, amely az elemek relatív sorrendjét tárolja, de az összes szomszédos elem, amely egyenlő, csak egyetlen elemre van szűrve.

## <a name="input"></a>Bevitel

### <a name="equal--tt---bool"></a>egyenlő: (nem, 'T) – > [bool](xref:microsoft.quantum.lang-ref.bool)

Olyan függvény, amely összehasonlítja a két olyan elemet, amely az `a` `b` IF értékkel egyenlőnek tekintendő `equal(a, b)` `true` .


### <a name="array--t"></a>tömb: 'T []

Az egyedi elemek szűrésére szolgáló tömb.



## <a name="output--t"></a>Kimenet: 'T []

Tömb, amely nem egyenlő szomszédos elemekből áll.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az egyes elemeinek típusa `array` .

## <a name="remarks"></a>Megjegyzések

Ha több olyan elem van, amely egyenlő, de nem egymás mellett van, akkor a kimeneti tömbben több esemény is szerepel.  Ezt a függvényt együtt használva `Sorted` egy teljes egyedi elemmel rendelkező tömböt kaphat.