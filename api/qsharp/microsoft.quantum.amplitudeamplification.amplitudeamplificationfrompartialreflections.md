---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificationFromPartialReflections függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: 8fa6db7d5616f8c561191e3da00a69b05041b279
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191686"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a><span data-ttu-id="886ab-102">AmplitudeAmplificationFromPartialReflections függvény</span><span class="sxs-lookup"><span data-stu-id="886ab-102">AmplitudeAmplificationFromPartialReflections function</span></span>

<span data-ttu-id="886ab-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="886ab-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="886ab-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="886ab-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="886ab-105">Az amplitúdó erősítése részleges reflexiók használatával.</span><span class="sxs-lookup"><span data-stu-id="886ab-105">Amplitude amplification by partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="886ab-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="886ab-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="886ab-107">fázisok: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="886ab-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="886ab-108">Részleges tükrözések fázisai</span><span class="sxs-lookup"><span data-stu-id="886ab-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="886ab-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="886ab-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="886ab-110">A Start állapottal kapcsolatos reflexiós operátor</span><span class="sxs-lookup"><span data-stu-id="886ab-110">Reflection operator about start state</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="886ab-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="886ab-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="886ab-112">Megcélzott állapottal kapcsolatos reflexiós operátor</span><span class="sxs-lookup"><span data-stu-id="886ab-112">Reflection operator about target state</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="886ab-113">Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="886ab-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="886ab-114">Egy művelet, amely az amplitúdó-erősítést részleges reflexiók használatával valósítja meg.</span><span class="sxs-lookup"><span data-stu-id="886ab-114">An operation that implements amplitude amplification by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="886ab-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="886ab-115">Remarks</span></span>

<span data-ttu-id="886ab-116">Az amplitúdó-erősítés olyan különleges eset, ha a rendszer nem rendelkezik qubits, és a feledékeny Oracle az identitásra van állítva.</span><span class="sxs-lookup"><span data-stu-id="886ab-116">Amplitude amplification is a special case of oblivious amplitude amplification where there are no system qubits and the oblivious oracle is set to identity.</span></span>
<span data-ttu-id="886ab-117">A legtöbb esetben az a $ `startQubits` \ket{\text{start}} $1 állapotú \_ , amely a $-$1 eigenstate lesz inicializálva `startStateReflection` .</span><span class="sxs-lookup"><span data-stu-id="886ab-117">In most cases, `startQubits` is initialized in the state $\ket{\text{start}}\_1$, which is the $-1$ eigenstate of `startStateReflection`.</span></span>