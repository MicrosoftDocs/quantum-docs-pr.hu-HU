---
uid: Microsoft.Quantum.Arrays.Exclude
title: Funkció kizárása
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 76cdee56e84951c63e80babfdca6a3de33583cab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848679"
---
# <a name="exclude-function"></a>Funkció kizárása

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy olyan tömböt ad vissza, amely egy másik tömb elemeit tartalmazza, és az indexek adott listáján szereplő elemeket is kizárja.

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>Bevitel

### <a name="remove--int"></a>eltávolítás: [int](xref:microsoft.quantum.lang-ref.int)[]

Az indexek tömbje, amely azt jelöli, hogy mely elemeket kell kizárni a kimenetből.


### <a name="array--t"></a>tömb: 'T []

Az a tömb, amely a kimeneti tömbben szereplő értékeket veszi fel.



## <a name="output--t"></a>Kimenet: 'T []

Egy olyan tömb `output` `output[0]` , amely az első eleme, `array` amelynek az indexe nem jelenik meg `remove` , például `output[1]` a második ilyen elem, és így tovább.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A tömb elemeinek típusa

## <a name="example"></a>Példa

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Exclude([1, 3, 4], array);
```