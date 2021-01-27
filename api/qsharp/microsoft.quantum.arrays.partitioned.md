---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Particionált függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: 43d99a0e33a813e4af23a3890ace808e91c1049c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845542"
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



## <a name="example"></a>Példa

```qsharp
// The following returns [[1, 5], [3], [7]];
let split = Partitioned([2,1], [1,5,3,7]);
```