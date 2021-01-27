---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedHpqTerm
title: _JWOptimizedHpqTerm művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedHpqTerm
qsharp.summary: Applies time-evolution by a PQ term described by a `GeneratorIndex`.
ms.openlocfilehash: b008315ded7cabc085e6d5da8f646e92914bf743
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854818"
---
# <a name="_jwoptimizedhpqterm-operation"></a><span data-ttu-id="9eb26-102">_JWOptimizedHpqTerm művelet</span><span class="sxs-lookup"><span data-stu-id="9eb26-102">_JWOptimizedHpqTerm operation</span></span>

<span data-ttu-id="9eb26-103">Névtér: [Microsoft. Quantum. Research. kémia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="9eb26-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="9eb26-104">Csomag: [Microsoft. Quantum. Research. kémia](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="9eb26-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="9eb26-105">Alkalmazza az idő-evolúciót az a által leírt PQ kifejezéssel `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="9eb26-105">Applies time-evolution by a PQ term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _JWOptimizedHpqTerm (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="9eb26-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9eb26-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="9eb26-107">kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="9eb26-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="9eb26-108">`GeneratorIndex` egy PQ kifejezést jelölő kifejezés.</span><span class="sxs-lookup"><span data-stu-id="9eb26-108">`GeneratorIndex` representing a PQ term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="9eb26-109">stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="9eb26-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="9eb26-110">Az idő időbeli alakulása.</span><span class="sxs-lookup"><span data-stu-id="9eb26-110">Duration of time-evolution.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="9eb26-111">parityQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9eb26-111">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9eb26-112">Qubit, amely meghatározza a Time-Evolution előjelét.</span><span class="sxs-lookup"><span data-stu-id="9eb26-112">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="9eb26-113">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9eb26-113">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9eb26-114">A Hamilton qubits.</span><span class="sxs-lookup"><span data-stu-id="9eb26-114">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9eb26-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9eb26-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

