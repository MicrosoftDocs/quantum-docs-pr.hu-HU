---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificationFromPartialReflections függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: fc7c2c0d05ea626f7f7e5d8ebf3ce5ecea61390b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721947"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="d3bab-102">AmplitudeAmplificationFromPartialReflections függvény</span><span class="sxs-lookup"><span data-stu-id="d3bab-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="d3bab-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="d3bab-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="d3bab-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d3bab-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d3bab-105">Az amplitúdó erősítése részleges reflexiók használatával.</span><span class="sxs-lookup"><span data-stu-id="d3bab-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="d3bab-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d3bab-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="d3bab-107">fázisok: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="d3bab-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="d3bab-108">Részleges tükrözések fázisai</span><span class="sxs-lookup"><span data-stu-id="d3bab-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="d3bab-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="d3bab-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="d3bab-110">A Start állapottal kapcsolatos reflexiós operátor</span><span class="sxs-lookup"><span data-stu-id="d3bab-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="d3bab-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="d3bab-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="d3bab-112">Megcélzott állapottal kapcsolatos reflexiós operátor</span><span class="sxs-lookup"><span data-stu-id="d3bab-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="d3bab-113">Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="d3bab-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="d3bab-114">Egy művelet, amely az amplitúdó-erősítést részleges reflexiók használatával valósítja meg.</span><span class="sxs-lookup"><span data-stu-id="d3bab-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="d3bab-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d3bab-115">Remarks</span></span>

<span data-ttu-id="d3bab-116">Az amplitúdó-erősítés olyan különleges eset, ha a rendszer nem rendelkezik qubits, és a feledékeny Oracle az identitásra van állítva.</span><span class="sxs-lookup"><span data-stu-id="d3bab-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="d3bab-117">A legtöbb esetben az a $ `startQubits` \ket{\text{start}} $1 állapotú \_ , amely a $-$1 eigenstate lesz inicializálva `startStateReflection` .</span><span class="sxs-lookup"><span data-stu-id="d3bab-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>