---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows-függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: adfea2b9a2f6c22446817538d29586284dba723e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842198"
---
# <a name="windows-function"></a>Windows-függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Az összes egymást követő altömbet adja vissza `size` .

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a>Leírás

Ez a függvény az összes olyan `n - size + 1` altömbt adja vissza `size` sorrendben, ahol a hossz a következő: `n` `arr` .
Az első altömb az utolsó altömbig tart `arr[0..size - 1], arr[1..size], arr[2..size + 1]` `arr[n - size..n - 1]` .

Ha `size <= 0` vagy `size > n` , üres tömböt ad vissza.

## <a name="input"></a>Bevitel

### <a name="size--int"></a>Méret: [int](xref:microsoft.quantum.lang-ref.int)

Az altömbök hossza.


### <a name="array--t"></a>tömb: 'T []

Elemek tömbje.



## <a name="output--t"></a>Kimenet: 'T [] []



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az elemek típusa `array` .

## <a name="example"></a>Példa

```qsharp
// same as [[1, 2, 3], [2, 3, 4], [3, 4, 5]]
let windows = Windows(3, [1, 2, 3, 4, 5]);
```