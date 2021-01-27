---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: EncodeOp-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: c9959f1afbd44df974c06b79f73eccd090b17985
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826176"
---
# <a name="encodeop-user-defined-type"></a><span data-ttu-id="9b4fd-102">EncodeOp-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="9b4fd-102">EncodeOp user defined type</span></span>

<span data-ttu-id="9b4fd-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="9b4fd-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="9b4fd-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b4fd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b4fd-105">Egy olyan műveletet jelöl, amely a fizikai regisztrációt logikai regiszterbe kódolja a megadott Scratch qubits használatával.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-105">Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.</span></span>

<span data-ttu-id="9b4fd-106">Az első argumentum a fizikai regiszter lesz, amely kódolva lesz, míg a második argumentum lesz a használni kívánt kaparós regisztráció.</span><span class="sxs-lookup"><span data-stu-id="9b4fd-106">The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.</span></span>

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```

