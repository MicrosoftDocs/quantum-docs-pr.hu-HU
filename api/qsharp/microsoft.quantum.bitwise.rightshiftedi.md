---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 5c3106eb73178554184cbfb37333c027805c69f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845257"
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

```qsharp
let c = a >>> b;
let c = RightShiftedI(a, b);
```