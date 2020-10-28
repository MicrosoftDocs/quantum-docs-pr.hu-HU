---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyAmplitudeAmplification
title: ApplyAmplitudeAmplification művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyAmplitudeAmplification
qsharp.summary: Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.
ms.openlocfilehash: be884eab70c7f72f994baf6bd7caf05769e0d5f2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721932"
---
# <a name="applyamplitudeamplification-operation"></a><span data-ttu-id="483a4-102">ApplyAmplitudeAmplification művelet</span><span class="sxs-lookup"><span data-stu-id="483a4-102">ApplyAmplitudeAmplification operation</span></span>

<span data-ttu-id="483a4-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="483a4-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="483a4-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="483a4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="483a4-105">Amplitúdó-erősítést alkalmaz egy adott regisztráción, a fázisok és az Oracle-alkalmazások adott készletének használatával, hogy tükrözze a kezdeti és a végső állapotot.</span><span class="sxs-lookup"><span data-stu-id="483a4-105">Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.</span></span>

```qsharp
operation ApplyAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, target : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="483a4-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="483a4-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="483a4-107">fázisok: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="483a4-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="483a4-108">Az amplitúdó-erősítési algoritmus egyes lépéseinek részleges tükrözéseit leíró fázisok összessége.</span><span class="sxs-lookup"><span data-stu-id="483a4-108">A set of phases describing the partial reflections at each step of the amplitude amplification algorithm.</span></span> <span data-ttu-id="483a4-109">Lásd: @"microsoft.quantum.amplitudeamplification.standardreflectionphases" példa.</span><span class="sxs-lookup"><span data-stu-id="483a4-109">See @"microsoft.quantum.amplitudeamplification.standardreflectionphases" for an example.</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="483a4-110">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="483a4-110">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="483a4-111">Egy Oracle, amely a kezdeti állapotot tükrözi.</span><span class="sxs-lookup"><span data-stu-id="483a4-111">An oracle that reflects about the initial state.</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="483a4-112">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="483a4-112">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="483a4-113">Egy Oracle, amely a kívánt végső állapotot tükrözi.</span><span class="sxs-lookup"><span data-stu-id="483a4-113">An oracle that reflects about the desired final state.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="483a4-114">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="483a4-114">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="483a4-115">Egy regisztráció, amely amplitúdó-erősítést hajt végre.</span><span class="sxs-lookup"><span data-stu-id="483a4-115">A register to perform amplitude amplification on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="483a4-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="483a4-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

