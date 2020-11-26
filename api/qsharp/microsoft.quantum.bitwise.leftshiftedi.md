---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3a7220489bfa241e2337df14291bafb1d6e0e19e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209859"
---
# <a name="leftshiftedi-function"></a>LeftShiftedI függvény

Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy adott számú biten hagyott szám bitenkénti-ábrázolását tolja át.

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>Bevitel

### <a name="value--int"></a>érték: [int](xref:microsoft.quantum.lang-ref.int)

Az a szám, amelynek a bitenkénti-ábrázolását balra kell átirányítani (jelentősebb).


### <a name="amount--int"></a>összeg: [int](xref:microsoft.quantum.lang-ref.int)

Azon bitek száma, amelyekről `value` balra kell váltani.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

A érték a `value` `amount` biten balra tolódott.

## <a name="remarks"></a>Megjegyzések

A következők egyenértékűek:

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```