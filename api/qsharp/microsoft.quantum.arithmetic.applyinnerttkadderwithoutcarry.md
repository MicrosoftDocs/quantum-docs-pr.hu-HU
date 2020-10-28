---
uid: Microsoft.Quantum.Arithmetic.ApplyInnerTTKAdderWithoutCarry
title: ApplyInnerTTKAdderWithoutCarry művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyInnerTTKAdderWithoutCarry
qsharp.summary: Implements the inner addition function for the operation RippleCarryAdderNoCarryTTK. This is the inner operation that is conjugated with the outer operation to construct the full adder.
ms.openlocfilehash: 3335c63b8509090deed1172419158da0d5e80409
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721648"
---
# <a name="applyinnerttkadderwithoutcarry-operation"></a>ApplyInnerTTKAdderWithoutCarry művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


Implementálja a belső hozzáadási funkciót a művelet RippleCarryAdderNoCarryTTK. Ez a belső művelet, amely a külső művelettel konjugált, hogy létrehozza a teljes kiegészítést.

```qsharp
operation ApplyInnerTTKAdderWithoutCarry (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Bevitel

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A LittleEndian qubit regisztrálja az első egész szám summand bemenetét a RippleCarryAdderNoCarryTTK.


### <a name="ys--littleendian"></a>[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :

A LittleEndian qubit regisztrálja a második egész summand-bemenetet a RippleCarryAdderNoCarryTTK.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A megadott vezérelt művelet a szimmetria és a műveletek kölcsönös megszüntetését teszi lehetővé az alapértelmezett implementációban, amely minden művelethez vezérlőelemet ad hozzá.

## <a name="references"></a>Referencia

- Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Quantum összeadás áramkörök és nem kötött ventilátorok", Quantum Information and kiszámítás, Vol. 10, 2010.
  https://arxiv.org/abs/0910.2530