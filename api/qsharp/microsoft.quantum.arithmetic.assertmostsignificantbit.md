---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 41381455d1a96970647f887e038f7dff3a4eb204
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223782"
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