---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 00d4f9151c620e044074930933ea2912b52534ed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219668"
---
# <a name="leftshiftedl-function"></a>LeftShiftedL függvény

Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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