---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Előtagok függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220388"
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