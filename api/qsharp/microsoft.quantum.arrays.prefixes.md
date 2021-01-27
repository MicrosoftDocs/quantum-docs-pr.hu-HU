---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Előtagok függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: a2e1721f8f59bf9aa425f04710637023d482a2ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845512"
---
# <a name="prefixes-function"></a>Előtagok függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A tömb megadott értéke az összes előtagjait adja vissza.

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a>Leírás

Az összes előtag tömbjét adja vissza, amely egy olyan tömbtől kezdődik, amely csak az első elemet tartalmazza, amíg a teljes tömb be nem fejeződik.

## <a name="input"></a>Bevitel

### <a name="array--t"></a>tömb: 'T []

Elemek tömbje.



## <a name="output--t"></a>Kimenet: 'T [] []



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az elemek típusa `array` .

## <a name="example"></a>Példa

```qsharp
let prefixes = Prefixes([23, 42, 144]);
// prefixes = [[23], [23, 42], [23, 42, 144]]
```