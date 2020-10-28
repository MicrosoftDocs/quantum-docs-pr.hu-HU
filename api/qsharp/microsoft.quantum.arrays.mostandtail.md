---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 8786250cf2f78ce2e9ff8baddc856d0bc07cb9a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718996"
---
# <a name="mostandtail-function"></a>MostAndTail függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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