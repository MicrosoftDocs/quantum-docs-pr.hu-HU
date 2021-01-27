---
uid: Microsoft.Quantum.Research.Chemistry._JWOptimizedFermionEvolution
title: _JWOptimizedFermionEvolution művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _JWOptimizedFermionEvolution
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 62fbd27f703a17a547d94e61c7a4981230a4b251
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854826"
---
# <a name="_jwoptimizedfermionevolution-operation"></a><span data-ttu-id="c730a-102">_JWOptimizedFermionEvolution művelet</span><span class="sxs-lookup"><span data-stu-id="c730a-102">_JWOptimizedFermionEvolution operation</span></span>

<span data-ttu-id="c730a-103">Névtér: [Microsoft. Quantum. Research. kémia](xref:Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c730a-103">Namespace: [Microsoft.Quantum.Research.Chemistry](xref:Microsoft.Quantum.Research.Chemistry)</span></span>

<span data-ttu-id="c730a-104">Csomag: [Microsoft. Quantum. Research. kémia](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="c730a-104">Package: [Microsoft.Quantum.Research.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)</span></span>


<span data-ttu-id="c730a-105">A dinamikus generátort szimulálható kapuk készlete jelöli, a JWOptimized pedig kibővíthető.</span><span class="sxs-lookup"><span data-stu-id="c730a-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JWOptimized basis.</span></span>

<span data-ttu-id="c730a-106">További részletekért lásd a [Dynamic Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) című témakört.</span><span class="sxs-lookup"><span data-stu-id="c730a-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation _JWOptimizedFermionEvolution (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, parityQubit : Qubit, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="c730a-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c730a-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="c730a-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="c730a-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="c730a-109">Az JWOptimized-alapú, egységes evolúcióként megjelenítendő generátor-index.</span><span class="sxs-lookup"><span data-stu-id="c730a-109">A generator index to be represented as unitary evolution in the JWOptimized basis.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="c730a-110">stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c730a-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c730a-111">Egy szorzó az időpontra, amely a (z)-ben hivatkozott kifejezés alapján alakul `generatorIndex` .</span><span class="sxs-lookup"><span data-stu-id="c730a-111">A multiplier on the duration of time-evolution by the term referenced in `generatorIndex`.</span></span>


### <a name="parityqubit--qubit"></a><span data-ttu-id="c730a-112">parityQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c730a-112">parityQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c730a-113">Qubit, amely meghatározza a Time-Evolution előjelét.</span><span class="sxs-lookup"><span data-stu-id="c730a-113">Qubit that determines the sign of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="c730a-114">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="c730a-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="c730a-115">A regisztráció az idő-Evolution operátorral végezhető el.</span><span class="sxs-lookup"><span data-stu-id="c730a-115">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c730a-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c730a-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

