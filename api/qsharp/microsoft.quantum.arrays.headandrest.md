---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848550"
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