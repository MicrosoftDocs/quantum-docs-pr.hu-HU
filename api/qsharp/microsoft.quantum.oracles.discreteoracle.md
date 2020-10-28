---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: DiscreteOracle-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: ccbcc92d4b6f1c800b576ad54739d26665e6d6d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724928"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="df030-102">DiscreteOracle-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="df030-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="df030-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="df030-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="df030-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="df030-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="df030-105">Diszkrét idejű Oracle-t jelöl.</span><span class="sxs-lookup"><span data-stu-id="df030-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="df030-106">Ez egy olyan Oracle, amely $U ^ millió dollárt valósít meg egy rögzített művelethez $U $ és egy nem negatív egész számú $m $ értékkel.</span><span class="sxs-lookup"><span data-stu-id="df030-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

