---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719152"
---
# <a name="indexrange-function"></a>IndexRange függvény

Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Csomag [](https://nuget.org/packages/)


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