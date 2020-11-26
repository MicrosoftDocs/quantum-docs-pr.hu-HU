---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 30e1cf6e353b8a4491e13a9e2f588ec9cc103cb4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191601"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="c5ec3-102">AmplitudeAmplificationFromStatePreparation függvény</span><span class="sxs-lookup"><span data-stu-id="c5ec3-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="c5ec3-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="c5ec3-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="c5ec3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5ec3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5ec3-105">A részleges reflexiók esetében az amplitúdó erősítése Oracle-támogatással.</span><span class="sxs-lookup"><span data-stu-id="c5ec3-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="c5ec3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c5ec3-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="c5ec3-107">fázisok: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="c5ec3-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="c5ec3-108">Részleges tükrözések fázisai</span><span class="sxs-lookup"><span data-stu-id="c5ec3-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="c5ec3-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="c5ec3-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="c5ec3-110">Az egységes Oracle $A $, amely előkészíti az indítási állapotot</span><span class="sxs-lookup"><span data-stu-id="c5ec3-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="c5ec3-111">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c5ec3-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c5ec3-112">Index a qubit jelzőhöz</span><span class="sxs-lookup"><span data-stu-id="c5ec3-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="c5ec3-113">Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="c5ec3-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="c5ec3-114">Olyan művelet, amely a részleges reflexiók által megvalósított Oracle-bővítést alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="c5ec3-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="c5ec3-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c5ec3-115">Remarks</span></span>

<span data-ttu-id="c5ec3-116">Ez szigorúbb feltételeket ró a kezdő és a cél állapotokra, mint a-ben `AmpAmpByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="c5ec3-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="c5ec3-117">Feltételezzük, hogy a megcélzott állapotot $ \ket f $ jelöléssel jelölte meg {1} \_ .</span><span class="sxs-lookup"><span data-stu-id="c5ec3-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="c5ec3-118">Feltételezzük, hogy a \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ Text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} a legtöbb esetben, `flagQubit` és `auxiliaryRegister` inicializálása a $ \ket {0} \_ {f} \ket {0} \_ s $ állapotban van.</span><span class="sxs-lookup"><span data-stu-id="c5ec3-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>