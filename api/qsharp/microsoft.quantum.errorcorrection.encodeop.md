---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: EncodeOp-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: 18d6df6037b1fe66a171acea1936fcb9ba1b27e5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200900"
---
# <a name="encodeop-user-defined-type"></a><span data-ttu-id="eeace-102">EncodeOp-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="eeace-102">EncodeOp user defined type</span></span>

<span data-ttu-id="eeace-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="eeace-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="eeace-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eeace-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eeace-105">Egy olyan műveletet jelöl, amely a fizikai regisztrációt logikai regiszterbe kódolja a megadott Scratch qubits használatával.</span><span class="sxs-lookup"><span data-stu-id="eeace-105">Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.</span></span>

<span data-ttu-id="eeace-106">Az első argumentum a fizikai regiszter lesz, amely kódolva lesz, míg a második argumentum lesz a használni kívánt kaparós regisztráció.</span><span class="sxs-lookup"><span data-stu-id="eeace-106">The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.</span></span>

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```

