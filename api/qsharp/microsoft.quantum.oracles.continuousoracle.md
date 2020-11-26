---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: ContinuousOracle-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: fb05e97c635ba75fc2d85dc2a7cea27f3a3af63f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226791"
---
# <a name="continuousoracle-user-defined-type"></a><span data-ttu-id="4188a-102">ContinuousOracle-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="4188a-102">ContinuousOracle user defined type</span></span>

<span data-ttu-id="4188a-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="4188a-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="4188a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4188a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4188a-105">Folyamatos Oracle-t jelöl.</span><span class="sxs-lookup"><span data-stu-id="4188a-105">Represents a continuous-time oracle.</span></span>

<span data-ttu-id="4188a-106">Ez egy Oracle, amely megvalósítja $U (\delta t): \ket{\psi (t)} \mapsto \ket{\psi (t + \delta t)} $ minden alkalommal $t $, ahol a $U $ egy rögzített művelet, ahol a $ \delta t $ értéke nem negatív valós szám.</span><span class="sxs-lookup"><span data-stu-id="4188a-106">This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.</span></span>

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

