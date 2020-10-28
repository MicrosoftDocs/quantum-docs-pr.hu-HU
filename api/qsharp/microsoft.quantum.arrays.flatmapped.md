---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: 3e75c7703471a2986812df660c2f9328f1536d22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719249"
---
# <a name="flatmapped-function"></a>FlatMapped függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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