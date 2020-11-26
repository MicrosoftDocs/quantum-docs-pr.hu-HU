---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b20a4a8c281a470af9a4828f8a5ca905a7918723
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209774"
---
# <a name="rightshiftedi-function"></a>RightShiftedI függvény

Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy szám bitenkénti-ábrázolását egy adott számú biten keresztül tolja.

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a>Bevitel

### <a name="value--int"></a>érték: [int](xref:microsoft.quantum.lang-ref.int)

Az a szám, amelynek a bitenkénti-ábrázolását jobbra (kevésbé jelentős) kell átirányítani.


### <a name="amount--int"></a>összeg: [int](xref:microsoft.quantum.lang-ref.int)

Azon bitek száma, amelyeknek `value` jobbra kell váltania.



## <a name="output--int"></a>Kimenet: [int](xref:microsoft.quantum.lang-ref.int)

A, a `value` bitek által jobbra eltolt érték `amount` .

## <a name="remarks"></a>Megjegyzések

A következők egyenértékűek:

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```