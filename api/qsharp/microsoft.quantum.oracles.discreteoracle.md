---
uid: Microsoft.Quantum.Oracles.DiscreteOracle
title: DiscreteOracle-felhasználó által definiált típus
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DiscreteOracle
qsharp.summary: >-
  Represents a discrete-time oracle.

  This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.
ms.openlocfilehash: 4b85f58889ef9cc55518009bdd9b59bdb2b5b842
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842578"
---
# <a name="discreteoracle-user-defined-type"></a><span data-ttu-id="7276c-102">DiscreteOracle-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="7276c-102">DiscreteOracle user defined type</span></span>

<span data-ttu-id="7276c-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="7276c-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="7276c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7276c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7276c-105">Diszkrét idejű Oracle-t jelöl.</span><span class="sxs-lookup"><span data-stu-id="7276c-105">Represents a discrete-time oracle.</span></span>

<span data-ttu-id="7276c-106">Ez egy olyan Oracle, amely $U ^ millió dollárt valósít meg egy rögzített művelethez $U $ és egy nem negatív egész számú $m $ értékkel.</span><span class="sxs-lookup"><span data-stu-id="7276c-106">This is an oracle that implements $U^m$ for a fixed operation $U$ and a non-negative integer $m$.</span></span>

```qsharp

newtype DiscreteOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```

