---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: e851e8503b3afcb4572f09fe39079247518c22c4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221249"
---
# <a name="flatmapped-function"></a>FlatMapped függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy tömb és egy függvény, amely egy tömb elemet képez egy kimeneti tömbhöz, visszaadja az összefűzött kimeneti tömböket minden egyes tömb elemhez.

```qsharp
function FlatMapped<'TInput, 'TOutput> (mapper : ('TInput -> 'TOutput[]), array : 'TInput[]) : 'TOutput[]
```


## <a name="input"></a>Bevitel

### <a name="mapper--tinput---toutput"></a>Mapper: ' TInput-> ' TOutput []

A-ből származó függvény, `'TInput` `'TOutput[]` amely a tömb elemeinek hozzárendelésére szolgál.


### <a name="array--tinput"></a>tömb: "TInput []

Elemek tömbje.



## <a name="output--toutput"></a>Kimenet: ' TOutput []

Egy tömb, `'TOutput[]` amely a leképezési függvény által generált összes tömb összefűzése.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="tinput"></a>'TInput

Az elemek típusa `array` .
### <a name="toutput"></a>'TOutput

A `mapper` függvény az ilyen típusú tömböket adja vissza.