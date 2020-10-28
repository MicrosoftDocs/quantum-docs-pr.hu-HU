---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 7725ff327e327578ff36242a2b1bc6d03fab0d0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721946"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="a90c2-102">AmplitudeAmplificationFromStatePreparation függvény</span><span class="sxs-lookup"><span data-stu-id="a90c2-102">AmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="a90c2-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="a90c2-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="a90c2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a90c2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a90c2-105">A részleges reflexiók esetében az amplitúdó erősítése Oracle-támogatással.</span><span class="sxs-lookup"><span data-stu-id="a90c2-105">Amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="a90c2-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a90c2-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="a90c2-107">fázisok: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="a90c2-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="a90c2-108">Részleges tükrözések fázisai</span><span class="sxs-lookup"><span data-stu-id="a90c2-108">Phases of partial reflections</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="a90c2-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="a90c2-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="a90c2-110">Az egységes Oracle $A $, amely előkészíti az indítási állapotot</span><span class="sxs-lookup"><span data-stu-id="a90c2-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="a90c2-111">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a90c2-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a90c2-112">Index a qubit jelzőhöz</span><span class="sxs-lookup"><span data-stu-id="a90c2-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="a90c2-113">Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="a90c2-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a90c2-114">Olyan művelet, amely a részleges reflexiók által megvalósított Oracle-bővítést alkalmaz.</span><span class="sxs-lookup"><span data-stu-id="a90c2-114">An operation that implements amplitude amplification by oracles that are implemented by partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="a90c2-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="a90c2-115">Remarks</span></span>

<span data-ttu-id="a90c2-116">Ez szigorúbb feltételeket ró a kezdő és a cél állapotokra, mint a-ben `AmpAmpByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="a90c2-116">This imposes stricter conditions on form of the start and target states than in `AmpAmpByReflectionPhases`.</span></span>
<span data-ttu-id="a90c2-117">Feltételezzük, hogy a megcélzott állapotot $ \ket f $ jelöléssel jelölte meg {1} \_ .</span><span class="sxs-lookup"><span data-stu-id="a90c2-117">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="a90c2-118">Feltételezzük, hogy a \begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ Text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} a legtöbb esetben, `flagQubit` és `auxiliaryRegister` inicializálása a $ \ket {0} \_ {f} \ket {0} \_ s $ állapotban van.</span><span class="sxs-lookup"><span data-stu-id="a90c2-118">It is assumed that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} In most cases, `flagQubit` and `auxiliaryRegister` are initialized in the state $\ket{0}\_{f}\ket{0}\_s$.</span></span>