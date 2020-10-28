---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedZZTerm
title: _JWOptimizedZZTerm művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedZZTerm
qsharp.summary: Applies time-evolution by a ZZ term described by a `GeneratorIndex`.
ms.openlocfilehash: 824918e06e54e31834019a396b310bbaa6beeb46
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722773"
---
# <a name="_jwoptimizedzzterm-operation"></a><span data-ttu-id="29d40-102">_JWOptimizedZZTerm művelet</span><span class="sxs-lookup"><span data-stu-id="29d40-102">_JWOptimizedZZTerm operation</span></span>

<span data-ttu-id="29d40-103">Névtér: [Microsoft. Quantum. Research. kémia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="29d40-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="29d40-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="29d40-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="29d40-105">Alkalmazza az időt – az evolúciót az a által leírt ZZ-kifejezéssel `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="29d40-105">Applies time-evolution by a ZZ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedZZTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="29d40-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="29d40-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="29d40-107">kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="29d40-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="29d40-108">`GeneratorIndex` a ZZ-kifejezést jelölő kifejezés.</span><span class="sxs-lookup"><span data-stu-id="29d40-108">`GeneratorIndex` representing a ZZ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="29d40-109">stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="29d40-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="29d40-110">Az idő időbeli alakulása.</span><span class="sxs-lookup"><span data-stu-id="29d40-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="29d40-111">parityQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="29d40-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="29d40-112">Qubit, amely meghatározza a Time-Evolution előjelét.</span><span class="sxs-lookup"><span data-stu-id="29d40-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="29d40-113">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="29d40-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="29d40-114">A Hamilton qubits.</span><span class="sxs-lookup"><span data-stu-id="29d40-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="29d40-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="29d40-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

