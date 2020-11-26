---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: MultiplyAndAddPhaseByModularInteger művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: 1ca20b525d2a76e554d5a2e8d4f40060b5ef51cf
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223867"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a>MultiplyAndAddPhaseByModularInteger művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ugyanaz, mint a MultiplyAndAddByModularInteger, de azt feltételezi, hogy a summand QFT-alapú egész számokat kódol.

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="constmultiplier--int"></a>constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)

Az egyes alapállapotok címkéjébe felvenni $a $ értéket.


### <a name="modulus--int"></a>modulus: [int](xref:microsoft.quantum.lang-ref.int)

Az a modulus $N $, amelyet a Hozzáadás és a szorzás is figyelembe vesz a tekintetében.


### <a name="multiplier--littleendian"></a>szorzó: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Egy olyan előjel nélküli egész szám, amelynek értékét fel kell venni az egyes alapállapotok címkéjébe `summand` .


### <a name="phasesummand--phaselittleendian"></a>phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

A művelet céljaként használandó, előjel nélküli egész számot jelölő kvantum-regisztráció.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

Feltételezi, hogy `phaseSummand` a legmagasabb bit 0 értékű.
Azt is feltételezi, hogy a értéke `phaseSummand` kisebb, mint $N $.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. aritmetika. MultiplyAndAddByModularInteger](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)