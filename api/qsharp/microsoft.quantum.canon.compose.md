---
uid: Microsoft.Quantum.Canon.Compose
title: Összeállítási függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 73eab66e2e9a9af56d01db927eb7af38bb56a23e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840911"
---
# <a name="compose-function"></a>Összeállítási függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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