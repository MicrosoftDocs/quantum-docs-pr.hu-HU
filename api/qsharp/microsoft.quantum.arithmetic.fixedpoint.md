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
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="7b978-102">FixedPoint-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="7b978-102">FixedPoint user defined type</span></span>

<span data-ttu-id="7b978-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="7b978-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="7b978-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7b978-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7b978-105">Egy rögzített pont számú qubits-kódolású regisztert jelöl.</span><span class="sxs-lookup"><span data-stu-id="7b978-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="7b978-106">Egy egész számból áll, amely egyenlő a bináris ponttól balra lévő qubits számával, azaz az 1 értéknél nagyobb vagy azzal egyenlő qubits, valamint a kvantum-regisztrációval.</span><span class="sxs-lookup"><span data-stu-id="7b978-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

