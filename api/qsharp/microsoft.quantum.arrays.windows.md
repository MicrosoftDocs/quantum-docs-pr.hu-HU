---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows-függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 8f32a23aa4379744b84c3b8d9c8f565e61c3c64e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219889"
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