---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Particionált függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220501"
---
# <a name="partitioned-function"></a>Particionált függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Tömb felosztása több részre.

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Bevitel

### <a name="nelements--int"></a>nElements: [int](xref:microsoft.quantum.lang-ref.int)[]

Elemek száma a tömb egyes részeiben


### <a name="arr--t"></a>ARR: 'T []

A feldarabolni kívánt bemeneti tömb.



## <a name="output--t"></a>Kimenet: 'T [] []

Több tömb, ahol az első tömb az első, `nElements[0]` `arr` a második tömb pedig a következő: `nElements[1]` `arr` Az utolsó tömb tartalmazni fogja az összes fennmaradó elemet.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

