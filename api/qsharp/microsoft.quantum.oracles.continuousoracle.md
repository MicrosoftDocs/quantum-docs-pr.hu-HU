---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: ContinuousOracle-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: 9bc9b4bbdab6905a6a79893b1d559425ac679400
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724313"
---
# <a name="continuousoracle-user-defined-type"></a><span data-ttu-id="eb274-102">ContinuousOracle-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="eb274-102">ContinuousOracle user defined type</span></span>

<span data-ttu-id="eb274-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="eb274-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="eb274-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eb274-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eb274-105">Folyamatos Oracle-t jelöl.</span><span class="sxs-lookup"><span data-stu-id="eb274-105">Represents a continuous-time oracle.</span></span>

<span data-ttu-id="eb274-106">Ez egy Oracle, amely megvalósítja $U (\delta t): \ket{\psi (t)} \mapsto \ket{\psi (t + \delta t)} $ minden alkalommal $t $, ahol a $U $ egy rögzített művelet, ahol a $ \delta t $ értéke nem negatív valós szám.</span><span class="sxs-lookup"><span data-stu-id="eb274-106">This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.</span></span>

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

