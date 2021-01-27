---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 18e85120647c5a1f41ccab5fbfb27ea602a279af
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843206"
---
# <a name="fixedpoint-user-defined-type"></a>FixedPoint-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)

Csomag: [Microsoft. Quantum. numerikus számok](https://nuget.org/packages/Microsoft.Quantum.Numerics)


Egy rögzített pont számú qubits-kódolású regisztert jelöl. Egy egész számból áll, amely egyenlő a bináris ponttól balra lévő qubits számával, azaz az 1 értéknél nagyobb vagy azzal egyenlő qubits, valamint a kvantum-regisztrációval.

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

