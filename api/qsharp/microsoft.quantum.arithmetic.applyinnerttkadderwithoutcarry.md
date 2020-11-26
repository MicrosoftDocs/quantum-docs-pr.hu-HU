---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: ApplyInnerTTKAdderWithoutCarry művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 656dc947ab88a7e7f1e8e8722c5262470307f7dc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190955"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a>ApplyInnerTTKAdderWithoutCarry művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Implementálja a belső hozzáadási funkciót a művelet RippleCarryAdderNoCarryTTK. Ez a belső művelet, amely a külső művelettel konjugált, hogy létrehozza a teljes kiegészítést.

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Bevitel

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A LittleEndian qubit regisztrálja az első egész szám summand bemenetét a RippleCarryAdderNoCarryTTK.


### <a name="ys--littleendian"></a>[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :

A LittleEndian qubit regisztrálja a második egész summand-bemenetet a RippleCarryAdderNoCarryTTK.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A megadott vezérelt művelet a szimmetria és a műveletek kölcsönös megszüntetését teszi lehetővé az alapértelmezett implementációban, amely minden művelethez vezérlőelemet ad hozzá.

## <a name="references"></a>Hivatkozások

- Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Quantum összeadás áramkörök és nem kötött ventilátorok", Quantum Information and kiszámítás, Vol. 10, 2010.
  https://arxiv.org/abs/0910.2530