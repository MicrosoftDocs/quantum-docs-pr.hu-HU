---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 03ed69c7151e62b91c4a036e301f99b45ce5ab62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842095"
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

```qsharp
let c = a >>> b;
let c = RightShiftedL(a, b);
```