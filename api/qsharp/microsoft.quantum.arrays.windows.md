---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows-függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718745"
---
# <a name="windows-function"></a>Windows-függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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