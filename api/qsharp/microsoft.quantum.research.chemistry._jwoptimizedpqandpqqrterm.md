---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedPQandPQQRTerm
title: _JWOptimizedPQandPQQRTerm művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedPQandPQQRTerm
qsharp.summary: Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.
ms.openlocfilehash: 97ae285ede38883f058b3e7609f9a26fb9e4340a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854772"
---
# <a name="_jwoptimizedpqandpqqrterm-operation"></a><span data-ttu-id="a3965-102">_JWOptimizedPQandPQQRTerm művelet</span><span class="sxs-lookup"><span data-stu-id="a3965-102">_JWOptimizedPQandPQQRTerm operation</span></span>

<span data-ttu-id="a3965-103">Névtér: [Microsoft. Quantum. Research. kémia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a3965-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="a3965-104">Csomag: [Microsoft. Quantum. Research. kémia](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="a3965-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="a3965-105">Alkalmazza az idő-evolúciót az a által leírt PQ vagy PQQR kifejezéssel `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="a3965-105">Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedPQandPQQRTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="a3965-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a3965-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="a3965-107">kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="a3965-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="a3965-108">`GeneratorIndex` PQ vagy PQQr kifejezést jelképez.</span><span class="sxs-lookup"><span data-stu-id="a3965-108">`GeneratorIndex` representing a PQ or PQQr term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="a3965-109">stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a3965-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a3965-110">Az idő időbeli alakulása.</span><span class="sxs-lookup"><span data-stu-id="a3965-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="a3965-111">parityQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a3965-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a3965-112">Qubit, amely meghatározza a Time-Evolution előjelét.</span><span class="sxs-lookup"><span data-stu-id="a3965-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a3965-113">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a3965-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a3965-114">A Hamilton qubits.</span><span class="sxs-lookup"><span data-stu-id="a3965-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a3965-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a3965-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

