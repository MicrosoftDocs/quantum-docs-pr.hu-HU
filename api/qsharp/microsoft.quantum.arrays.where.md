---
uid: Microsoft.Quantum.Arrays.Where
title: Where függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 97598aa25d2d085aaab94f3d60ee64db9e2b89d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219923"
---
# <a name="where-function"></a>Where függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy predikátum és egy tömb miatt a tömb azon indexeit adja vissza, amelyekben a predikátum igaz.

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a>Bevitel

### <a name="predicate--t---bool"></a>predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)

Az `'T` elemek szűréséhez használt logikai értékből származó függvény.


### <a name="array--t"></a>tömb: 'T []

Elemek tömbje `'T` .



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]

Az indexek tömbje, ahol `predicate` igaz.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

Az elemek típusa `array` .