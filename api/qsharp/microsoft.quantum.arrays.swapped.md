---
uid: Microsoft.Quantum.Arrays.Swapped
title: Felcserélt függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 173fb32b5a41ce054f19548a7fcca18c11c4c4cd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220127"
---
# <a name="swapped-function"></a>Felcserélt függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy tömb két elemének kicserélt változatát alkalmazza.

```qsharp
function Swapped<'T> (firstIndex : Int, secondIndex : Int, arr : 'T[]) : 'T[]
```


## <a name="input"></a>Bevitel

### <a name="firstindex--int"></a>firstIndex: [int](xref:microsoft.quantum.lang-ref.int)

Az elsőként felcserélni kívánt elem indexe.


### <a name="secondindex--int"></a>secondIndex: [int](xref:microsoft.quantum.lang-ref.int)

A felcserélni kívánt második elem indexe.


### <a name="arr--t"></a>ARR: 'T []

A felcserélni kívánt elemeket tartalmazó tömb.



## <a name="output--t"></a>Kimenet: 'T []

Az a tömb, amelyben a helyszíni swap alkalmazva van.

## <a name="example"></a>Példa

```qsharp
// The following returns [0, 3, 2, 1, 4]
Swapped(1, 3, [0, 1, 2, 3, 4]);
```

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

