---
uid: Microsoft.Quantum.Arrays.Unique
title: Egyedi függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: 7964d5d41eb68cb05f9414164d69496c1f76eb08
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220008"
---
# <a name="unique-function"></a>Egyedi függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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