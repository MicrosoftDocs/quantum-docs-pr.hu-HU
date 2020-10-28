---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: EncodeOp-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: da947cdc25cb0edd3a4144022bbfc6ecb84c647f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712352"
---
# <a name="encodeop-user-defined-type"></a><span data-ttu-id="7f68a-102">EncodeOp-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="7f68a-102">EncodeOp user defined type</span></span>

<span data-ttu-id="7f68a-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="7f68a-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="7f68a-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7f68a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7f68a-105">Egy olyan műveletet jelöl, amely a fizikai regisztrációt logikai regiszterbe kódolja a megadott Scratch qubits használatával.</span><span class="sxs-lookup"><span data-stu-id="7f68a-105">Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.</span></span>

<span data-ttu-id="7f68a-106">Az első argumentum a fizikai regiszter lesz, amely kódolva lesz, míg a második argumentum lesz a használni kívánt kaparós regisztráció.</span><span class="sxs-lookup"><span data-stu-id="7f68a-106">The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.</span></span>

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```

