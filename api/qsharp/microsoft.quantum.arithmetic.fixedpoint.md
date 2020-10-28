---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: f1370cd2f8a7d6488ae0f6be841abd95e61f038e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721145"
---
# <a name="fixedpoint-user-defined-type"></a>FixedPoint-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag [](https://nuget.org/packages/)


Egy rögzített pont számú qubits-kódolású regisztert jelöl. Egy egész számból áll, amely egyenlő a bináris ponttól balra lévő qubits számával, azaz az 1 értéknél nagyobb vagy azzal egyenlő qubits, valamint a kvantum-regisztrációval.

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

