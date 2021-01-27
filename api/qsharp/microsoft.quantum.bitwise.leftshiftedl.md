---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 014653011574d0fabb4b9aa04cedf58b87ddf798
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842141"
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

```qsharp
let c = a <<< b;
let c = LeftShiftedL(a, b);
```