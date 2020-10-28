---
uid: Microsoft.Quantum.ErrorCorrection.RecoveryFn
title: RecoveryFn-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: RecoveryFn
qsharp.summary: Type for function that maps an error syndrome to a sequence of `Pauli[]` operations that correct the detected error.
ms.openlocfilehash: 6f4db7312fadbd8ca4c6b8533f78c2c5a886f30e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712198"
---
# <a name="recoveryfn-user-defined-type"></a><span data-ttu-id="0c75d-102">RecoveryFn-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="0c75d-102">RecoveryFn user defined type</span></span>

<span data-ttu-id="0c75d-103">Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="0c75d-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="0c75d-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0c75d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0c75d-105">Írja be azt a függvényt, amely a hibás szindrómát leképező műveletek egy olyan sorára mutat, `Pauli[]` amely az észlelt hibát javította.</span><span class="sxs-lookup"><span data-stu-id="0c75d-105">Type for function that maps an error syndrome to a sequence of `Pauli[]` operations that correct the detected error.</span></span>

```qsharp

newtype RecoveryFn = ((Microsoft.Quantum.ErrorCorrection.Syndrome -> Pauli[]));
```

