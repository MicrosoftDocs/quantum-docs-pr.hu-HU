---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZTerm
title: _JWOptimizedZTerm művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZTerm
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: 0b54bd7916ff8294501716365c11211b4654f5ad
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722787"
---
# <a name="_jwoptimizedzterm-operation"></a><span data-ttu-id="cd388-102">_JWOptimizedZTerm művelet</span><span class="sxs-lookup"><span data-stu-id="cd388-102">_JWOptimizedZTerm operation</span></span>

<span data-ttu-id="cd388-103">Névtér: [Microsoft. Quantum. Research. kémia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="cd388-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="cd388-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cd388-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cd388-105">Alkalmazza az idő-evolúciót az a által leírt Z kifejezéssel `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="cd388-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="cd388-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="cd388-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="cd388-107">kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="cd388-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="cd388-108">`GeneratorIndex` egy Z kifejezést jelképez.</span><span class="sxs-lookup"><span data-stu-id="cd388-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="cd388-109">stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cd388-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cd388-110">Az idő időbeli alakulása.</span><span class="sxs-lookup"><span data-stu-id="cd388-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="cd388-111">parityQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cd388-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="cd388-112">Qubit, amely meghatározza a Time-Evolution előjelét.</span><span class="sxs-lookup"><span data-stu-id="cd388-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="cd388-113">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="cd388-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="cd388-114">A Hamilton qubits.</span><span class="sxs-lookup"><span data-stu-id="cd388-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cd388-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cd388-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

