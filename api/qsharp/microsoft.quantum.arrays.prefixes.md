---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Előtagok függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718937"
---
# <a name="prefixes-function"></a>Előtagok függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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