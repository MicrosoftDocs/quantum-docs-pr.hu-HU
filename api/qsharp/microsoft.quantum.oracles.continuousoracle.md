---
uid: Microsoft.Quantum.Oracles.ContinuousOracle
title: ContinuousOracle-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ContinuousOracle
qsharp.summary: >-
  Represents a continuous-time oracle.

  This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.
ms.openlocfilehash: ac254b7556878550216d5c0c9222620fdc5c5702
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855932"
---
# <a name="continuousoracle-user-defined-type"></a><span data-ttu-id="67622-102">ContinuousOracle-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="67622-102">ContinuousOracle user defined type</span></span>

<span data-ttu-id="67622-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="67622-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="67622-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67622-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67622-105">Folyamatos Oracle-t jelöl.</span><span class="sxs-lookup"><span data-stu-id="67622-105">Represents a continuous-time oracle.</span></span>

<span data-ttu-id="67622-106">Ez egy Oracle, amely megvalósítja $U (\delta t): \ket{\psi (t)} \mapsto \ket{\psi (t + \delta t)} $ minden alkalommal $t $, ahol a $U $ egy rögzített művelet, ahol a $ \delta t $ értéke nem negatív valós szám.</span><span class="sxs-lookup"><span data-stu-id="67622-106">This is an oracle that implements $U(\delta t) : \ket{\psi(t)} \mapsto \ket{\psi(t + \delta t)}$ for all times $t$, where $U$ is a fixed operation, and where $\delta t$ is a non-negative real number.</span></span>

```qsharp

newtype ContinuousOracle = (((Double, Qubit[]) => Unit is Adj + Ctl));
```

