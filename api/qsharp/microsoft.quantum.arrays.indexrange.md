---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845781"
---
# <a name="indexrange-function"></a>IndexRange függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Egy tömb esetében az adott tömb indexei között egy tartományt ad vissza, amely a for ciklusban használható.

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a>Bevitel

### <a name="array--telement"></a>tömb: "táv []

Olyan tömb, amelynek vissza kell adni az indexek tartományát.



## <a name="output--range"></a>Kimenet: [tartomány](xref:microsoft.quantum.lang-ref.range)

Egy tartomány az összes indexben a tömbben.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="telement"></a>"Táv

A tömb elemeinek típusa.

## <a name="example"></a>Példa

A következő `for` hurkok egyenértékűek:

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```