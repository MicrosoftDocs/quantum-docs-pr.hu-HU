---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 1144e00227df1cd7d96bc76b118b0b556adbaa96
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221079"
---
# <a name="headandrest-function"></a>HeadAndRest függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Az első és a tömb összes többi elemének egy rekordját adja vissza.

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a>Bevitel

### <a name="array--a"></a>tömb: "A []

Legalább egy elemet tartalmazó tömb.



## <a name="output--aa"></a>Kimenet: ("A", "A []"

A tömb első és összes többi elemének egy rekordja.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="a"></a>"A

A tömb elemeinek típusa