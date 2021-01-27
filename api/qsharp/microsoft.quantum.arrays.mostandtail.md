---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: fd5569f1b71ac2fdf2b5c08ba7dde172e3a6744e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845588"
---
# <a name="mostandtail-function"></a>MostAndTail függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A tömb összes, de utolsó elemének egy rekordját adja vissza.

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a>Bevitel

### <a name="array--a"></a>tömb: "A []

Legalább egy elemet tartalmazó tömb.



## <a name="output--aa"></a>Kimenet: ("A []," A)

A tömb összes, de utolsó elemének egy rekordja.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="a"></a>"A

A tömb elemeinek típusa