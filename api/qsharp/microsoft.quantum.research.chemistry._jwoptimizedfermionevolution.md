---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedFermionEvolution
title: _JWOptimizedFermionEvolution művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedFermionEvolution
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 5976b65d44c0e8597088dbaa6b85ffde634edcdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722800"
---
# <a name="_jwoptimizedfermionevolution-operation"></a><span data-ttu-id="ca4c3-102">_JWOptimizedFermionEvolution művelet</span><span class="sxs-lookup"><span data-stu-id="ca4c3-102">_JWOptimizedFermionEvolution operation</span></span>

<span data-ttu-id="ca4c3-103">Névtér: [Microsoft. Quantum. Research. kémia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="ca4c3-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="ca4c3-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ca4c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ca4c3-105">A dinamikus generátort szimulálható kapuk készlete jelöli, a JWOptimized pedig kibővíthető.</span><span class="sxs-lookup"><span data-stu-id="ca4c3-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

<span data-ttu-id="ca4c3-106">További részletekért lásd a [Dynamic Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) című témakört.</span><span class="sxs-lookup"><span data-stu-id="ca4c3-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation _JWOptimizedFermionEvolution (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="ca4c3-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ca4c3-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="ca4c3-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="ca4c3-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="ca4c3-109">Az JWOptimized-alapú, egységes evolúcióként megjelenítendő generátor-index.</span><span class="sxs-lookup"><span data-stu-id="ca4c3-109">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="ca4c3-110">stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ca4c3-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ca4c3-111">Egy szorzó az időpontra, amely a (z)-ben hivatkozott kifejezés alapján alakul `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="ca4c3-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="ca4c3-112">parityQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ca4c3-112">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ca4c3-113">Qubit, amely meghatározza a Time-Evolution előjelét.</span><span class="sxs-lookup"><span data-stu-id="ca4c3-113">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="ca4c3-114">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ca4c3-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ca4c3-115">A regisztráció az idő-Evolution operátorral végezhető el.</span><span class="sxs-lookup"><span data-stu-id="ca4c3-115">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ca4c3-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ca4c3-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

