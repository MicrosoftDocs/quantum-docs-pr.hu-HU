---
uid: Microsoft.Quantum.ErrorCorrection.DecodeOp
title: DecodeOp-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeOp
qsharp.summary: >-
  Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.

  The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.
ms.openlocfilehash: 2b3d4558f6528c2e0f597398d12fc9331ab381b5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827375"
---
# <a name="decodeop-user-defined-type"></a><span data-ttu-id="4cdba-102">DecodeOp-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="4cdba-102">DecodeOp user defined type</span></span>

<span data-ttu-id="4cdba-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="4cdba-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="4cdba-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4cdba-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4cdba-105">Egy olyan műveletet jelöl, amely kódolja a kódolt regisztrációt egy fizikai regiszterbe, valamint a tünetegyüttes rögzítéséhez használt qubits.</span><span class="sxs-lookup"><span data-stu-id="4cdba-105">Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.</span></span>

<span data-ttu-id="4cdba-106">Egy DecodeOp argumentuma megegyezik egy EncodeOp való visszatéréssel, és fordítva.</span><span class="sxs-lookup"><span data-stu-id="4cdba-106">The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.</span></span>

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```

