---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 3d941e1a0bcd96fe54ab01019293d883f11547a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219515"
---
# <a name="rightshiftedl-function"></a>RightShiftedL függvény

Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy szám bitenkénti-ábrázolását egy adott számú biten keresztül tolja.

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a>Bevitel

### <a name="value--bigint"></a>érték: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

Az a szám, amelynek a bitenkénti-ábrázolását jobbra (kevésbé jelentős) kell átirányítani.


### <a name="amount--int"></a>összeg: [int](xref:microsoft.quantum.lang-ref.int)

Azon bitek száma, amelyeknek `value` jobbra kell váltania.



## <a name="output--bigint"></a>Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)

A, a `value` bitek által jobbra eltolt érték `amount` .

## <a name="remarks"></a>Megjegyzések

A következők egyenértékűek:

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```