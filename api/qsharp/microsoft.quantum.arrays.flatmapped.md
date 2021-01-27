---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: bee7002c5a1e80cee7907ff9cb4ebaaedf8e9923
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848640"
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

## <a name="example"></a>Példa

```qsharp
let Numbers = SequenceI(1, _); // generates numbers starting from 1
let values = FlatMapped(Numbers, [1, 2, 3]);
// values = [1, 1, 2, 1, 2, 3]
```