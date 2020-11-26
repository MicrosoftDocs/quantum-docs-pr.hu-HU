---
uid: Microsoft.Quantum.ErrorCorrection.DecodeOp
title: DecodeOp-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeOp
qsharp.summary: >-
  Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.

  The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.
ms.openlocfilehash: f1fc2851b7ed8b12cf8a47fabe794235a3083d31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201002"
---
# <a name="decodeop-user-defined-type"></a><span data-ttu-id="1e382-102">DecodeOp-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="1e382-102">DecodeOp user defined type</span></span>

<span data-ttu-id="1e382-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="1e382-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="1e382-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1e382-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1e382-105">Egy olyan műveletet jelöl, amely kódolja a kódolt regisztrációt egy fizikai regiszterbe, valamint a tünetegyüttes rögzítéséhez használt qubits.</span><span class="sxs-lookup"><span data-stu-id="1e382-105">Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.</span></span>

<span data-ttu-id="1e382-106">Egy DecodeOp argumentuma megegyezik egy EncodeOp való visszatéréssel, és fordítva.</span><span class="sxs-lookup"><span data-stu-id="1e382-106">The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.</span></span>

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

