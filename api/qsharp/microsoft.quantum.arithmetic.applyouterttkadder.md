---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterTTKAdder
title: ApplyOuterTTKAdder művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterTTKAdder
qsharp.summary: Implements the outer operation for RippleCarryAdderTTK to conjugate the inner operation to construct the full adder.
ms.openlocfilehash: 3d6d7c3446075130e5a8ee93abbd27e617d50b3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721564"
---
# <a name="applyouterttkadder-operation"></a>ApplyOuterTTKAdder művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


Implementálja a külső műveletet a RippleCarryAdderTTK a belső művelet a teljes kiegészítés létrehozásához a konjugátumban.

```qsharp
operation ApplyOuterTTKAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Bevitel

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

A LittleEndian qubit regisztrálja az első egész szám summand bemenetét a RippleCarryAdderTTK.


### <a name="ys--littleendian"></a>[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :

A LittleEndian qubit regisztrálja a második egész summand-bemenetet a RippleCarryAdderTTK.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referencia

- Yasuhiro Takahashi, Seiichiro tani, Noboru Kunihiro: "Quantum összeadás áramkörök és nem kötött ventilátorok", Quantum Information and kiszámítás, Vol. 10, 2010.
  https://arxiv.org/abs/0910.2530