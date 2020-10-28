---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 17e5c845755f74e9703381bc82bfd63be836d038
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718636"
---
# <a name="leftshiftedl-function"></a>LeftShiftedL függvény

Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)

Csomag [](https://nuget.org/packages/)


Egy adott számú biten hagyott szám bitenkénti-ábrázolását tolja át.

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>Bevitel

### <a name="value--bigint"></a>érték: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Az a szám, amelynek a bitenkénti-ábrázolását balra kell átirányítani (jelentősebb).


### <a name="amount--int"></a>összeg: [int](xref:microsoft.quantum.lang-ref.int)

Azon bitek száma, amelyekről `value` balra kell váltani.



## <a name="output--bigint"></a>Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

A érték a `value` `amount` biten balra tolódott.

## <a name="remarks"></a>Megjegyzések

A következők egyenértékűek:

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```