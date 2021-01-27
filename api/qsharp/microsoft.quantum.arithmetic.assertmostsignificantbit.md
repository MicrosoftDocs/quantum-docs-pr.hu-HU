---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: b0b52a4ba7492d68896669aeb0b6b550d2f27f64
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843423"
---
# <a name="assertmostsignificantbit-operation"></a>AssertMostSignificantBit művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Azt állítja be, hogy egy qubit-regiszter legjelentősebb qubit, amely egy előjel nélküli egész számot jelöl, egy adott állapotban van.

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="value--__invalidresult__"></a>érték: __érvénytelen <Result>__

Az érvényesített legmagasabb bit értéke.


### <a name="number--littleendian"></a>szám: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Előjel nélküli egész szám, amelynek a legmagasabb bit be van jelölve.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A művelet ellenőrzött verziója figyelmen kívül hagyja a vezérlőket.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. belső. érvényesítés](xref:Microsoft.Quantum.Intrinsic.Assert)