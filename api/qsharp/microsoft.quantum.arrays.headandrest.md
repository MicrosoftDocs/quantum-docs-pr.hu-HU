---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719177"
---
# <a name="headandrest-function"></a>HeadAndRest függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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