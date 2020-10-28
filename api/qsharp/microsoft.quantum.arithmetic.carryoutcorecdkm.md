---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: CarryOutCoreCDKM művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 6a292e66f6d9911d2a9075f6397f4f5ba97ec64d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721301"
---
# <a name="carryoutcorecdkm-operation"></a>CarryOutCoreCDKM művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


A RippleCarryAdderCDKM a fenti ApplyOuterCDKMAdder művelettel használt alapművelete, azaz a művelettel konjugált a RippleCarryAdderCDKM belső működésének beszerzéséhez. Ez a művelet kiszámítja a végrehajtás qubit, és a bemenet egy részén a nem kapuk sorozatot alkalmazza `ys` .

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit
```


## <a name="input"></a>Bevitel

### <a name="xs--littleendian"></a>xs: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Első qubit-regisztráció.


### <a name="ys--littleendian"></a>[LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) :

Második qubit-regisztráció.


### <a name="ancilla--qubit"></a>Ancilla: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

A RippleCarryAdderCDKM a műveletnek átadott Ancilla-qubit használja.


### <a name="carry--qubit"></a>Carry: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Végezze el a qubit a RippleCarryAdderCDKM műveletben.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Referencia

- Steven A. Cuccaro, Thomas G. Drapérier, Samuel A. Kutin, David Petra Moulton: "egy új kvantum-hullám-Carry összeadás Circuit", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1