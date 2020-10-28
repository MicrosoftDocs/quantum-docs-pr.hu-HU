---
uid: Microsoft.Quantum.Canon.Compose
title: Összeállítási függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 02cff7eef4d55d27d5d72e6219a90b7d8f5beb3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716496"
---
# <a name="compose-function"></a>Összeállítási függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Két függvény összeállítását adja vissza.

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a>Leírás

A $f $ és a $g $ függvényben a megadott függvények egy új függvényt adnak vissza, amely az $f \circ g $ értéket jelképezi.

## <a name="input"></a>Bevitel

### <a name="outer--u---v"></a>külső: "U->" V

Az alkalmazni kívánt második függvény.


### <a name="inner--t---u"></a>belső: nem > U

Az elsőként alkalmazandó függvény.



## <a name="output--t---v"></a>Kimenet: nem > ' V

Egy új függvény $h $, amely minden bemenethez $x $, $f (g (x)) = h (x) $.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az elsőként alkalmazandó függvény bemeneti típusa.
### <a name="u"></a>' U

Az elsőként alkalmazandó függvény kimeneti típusa és az alkalmazandó második függvény bemeneti típusa.
### <a name="v"></a>"V

Az alkalmazni kívánt második függvény kimeneti típusa.