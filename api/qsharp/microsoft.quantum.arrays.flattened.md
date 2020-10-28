---
uid: Microsoft.Quantum.Arrays.Flattened
title: Összeolvasztott függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 91a35f0ac2c2f8609bac07734265fcf4e88bf50b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719237"
---
# <a name="flattened-function"></a>Összeolvasztott függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


A tömbök tömbje az összes tömb összefűzését adja vissza.

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a>Bevitel

### <a name="arrays--t"></a>tömbök: 'T [] []

Tömbök tömbje.



## <a name="output--t"></a>Kimenet: 'T []

Az összes tömb összefűzése.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az elemek típusa `array` .