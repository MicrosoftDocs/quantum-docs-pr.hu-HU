---
uid: Microsoft.Quantum.Arrays.Exclude
title: Funkció kizárása
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: e1fa7e728d4846db90872055454a8182a77a518b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719284"
---
# <a name="exclude-function"></a>Funkció kizárása

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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