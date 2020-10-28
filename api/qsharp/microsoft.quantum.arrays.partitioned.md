---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Particionált függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: e3395afeda206e255a58175b57245f91c588d978
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718973"
---
# <a name="partitioned-function"></a>Particionált függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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

