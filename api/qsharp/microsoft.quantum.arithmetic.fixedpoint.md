---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 0fea6e4ee1b8c5391e815217f1ddf9e511d46463
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223102"
---
# <a name="fixedpoint-user-defined-type"></a>FixedPoint-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Egy rögzített pont számú qubits-kódolású regisztert jelöl. Egy egész számból áll, amely egyenlő a bináris ponttól balra lévő qubits számával, azaz az 1 értéknél nagyobb vagy azzal egyenlő qubits, valamint a kvantum-regisztrációval.

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

