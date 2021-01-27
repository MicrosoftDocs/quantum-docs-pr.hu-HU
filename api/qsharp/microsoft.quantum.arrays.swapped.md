---
uid: Microsoft.Quantum.Arrays.Swapped
title: Felcserélt függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Swapped
qsharp.summary: Applies a swap of two elements in an array.
ms.openlocfilehash: 575d6b76e52f198d91ab5557ada8032df491cfa3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850952"
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

