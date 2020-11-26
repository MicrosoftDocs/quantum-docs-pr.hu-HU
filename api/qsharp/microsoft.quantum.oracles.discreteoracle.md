---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: DiscreteOracle-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: accbd7b88cc2f6522da20ec1959492310ff0e743
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193896"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="2d366-102">DiscreteOracle-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="2d366-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="2d366-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="2d366-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="2d366-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2d366-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2d366-105">Diszkrét idejű Oracle-t jelöl.</span><span class="sxs-lookup"><span data-stu-id="2d366-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="2d366-106">Ez egy olyan Oracle, amely $U ^ millió dollárt valósít meg egy rögzített művelethez $U $ és egy nem negatív egész számú $m $ értékkel.</span><span class="sxs-lookup"><span data-stu-id="2d366-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

