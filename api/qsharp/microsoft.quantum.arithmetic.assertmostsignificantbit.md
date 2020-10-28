---
uid: Microsoft.Quantum.Arithmetic.AssertMostSignificantBit
title: AssertMostSignificantBit művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertMostSignificantBit
qsharp.summary: Asserts that the most significant qubit of a qubit register representing an unsigned integer is in a particular state.
ms.openlocfilehash: 408e50ed9f2e6c8ba35db20855608d2bd1f24eea
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721384"
---
# <a name="assertmostsignificantbit-operation"></a>AssertMostSignificantBit művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


Azt állítja be, hogy egy qubit-regiszter legjelentősebb qubit, amely egy előjel nélküli egész számot jelöl, egy adott állapotban van.

```qsharp
operation AssertMostSignificantBit (value : Result, number : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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