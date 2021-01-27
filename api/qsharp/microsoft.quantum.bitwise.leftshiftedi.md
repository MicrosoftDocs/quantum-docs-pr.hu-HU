---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3f551bdba5c8e2a1456838769e4cee0660d0f969
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845309"
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

```qsharp
let c = a <<< b;
let c = LeftShiftedI(a, b);
```