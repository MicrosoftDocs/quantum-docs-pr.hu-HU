---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: CarryOutCoreCDKM művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 19a692a3b54a413f25a474c361e773ab6c65579e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223544"
---
# <a name="carryoutcorecdkm-operation"></a>CarryOutCoreCDKM művelet

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A RippleCarryAdderCDKM a fenti ApplyOuterCDKMAdder művelettel használt alapművelete, azaz a művelettel konjugált a RippleCarryAdderCDKM belső működésének beszerzéséhez. Ez a művelet kiszámítja a végrehajtás qubit, és a bemenet egy részén a nem kapuk sorozatot alkalmazza `ys` .

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit is Adj + Ctl
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



## <a name="references"></a>Hivatkozások

- Steven A. Cuccaro, Thomas G. Drapérier, Samuel A. Kutin, David Petra Moulton: "egy új kvantum-hullám-Carry összeadás Circuit", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1