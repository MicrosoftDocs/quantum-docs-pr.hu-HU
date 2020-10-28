---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedPQandPQQRTerm
title: _JWOptimizedPQandPQQRTerm művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedPQandPQQRTerm
qsharp.summary: Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.
ms.openlocfilehash: 9d9f0d17c091ae771702e4047d17e1769d6bb294
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722143"
---
# <a name="_jwoptimizedpqandpqqrterm-operation"></a><span data-ttu-id="56d86-102">_JWOptimizedPQandPQQRTerm művelet</span><span class="sxs-lookup"><span data-stu-id="56d86-102">_JWOptimizedPQandPQQRTerm operation</span></span>

<span data-ttu-id="56d86-103">Névtér: [Microsoft. Quantum. Research. kémia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="56d86-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="56d86-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="56d86-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="56d86-105">Alkalmazza az idő-evolúciót az a által leírt PQ vagy PQQR kifejezéssel `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="56d86-105">Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedPQandPQQRTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="56d86-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="56d86-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="56d86-107">kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="56d86-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="56d86-108">`GeneratorIndex` PQ vagy PQQr kifejezést jelképez.</span><span class="sxs-lookup"><span data-stu-id="56d86-108">`GeneratorIndex` representing a PQ or PQQr term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="56d86-109">stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="56d86-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="56d86-110">Az idő időbeli alakulása.</span><span class="sxs-lookup"><span data-stu-id="56d86-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="56d86-111">parityQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="56d86-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="56d86-112">Qubit, amely meghatározza a Time-Evolution előjelét.</span><span class="sxs-lookup"><span data-stu-id="56d86-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="56d86-113">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="56d86-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="56d86-114">A Hamilton qubits.</span><span class="sxs-lookup"><span data-stu-id="56d86-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="56d86-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="56d86-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

