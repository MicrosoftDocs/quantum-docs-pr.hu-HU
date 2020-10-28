---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 9975d26af8f9beb2b91e409ad78159d6f04936e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721834"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a><span data-ttu-id="03791-102">ObliviousAmplitudeAmplificationFromStatePreparation függvény</span><span class="sxs-lookup"><span data-stu-id="03791-102">ObliviousAmplitudeAmplificationFromStatePreparation function</span></span>

<span data-ttu-id="03791-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="03791-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="03791-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="03791-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="03791-105">A részleges reflexiók esetében az amplitúdó-erősítést az Oracles okozta.</span><span class="sxs-lookup"><span data-stu-id="03791-105">Oblivious amplitude amplification by oracles for partial reflections.</span></span>

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="03791-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="03791-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="03791-107">fázisok: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="03791-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="03791-108">Részleges tükrözések fázisai</span><span class="sxs-lookup"><span data-stu-id="03791-108">Phases of partial reflections</span></span>


### <a name="startstateoracle--deterministicstateoracle"></a><span data-ttu-id="03791-109">startStateOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span><span class="sxs-lookup"><span data-stu-id="03791-109">startStateOracle : [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)</span></span>

<span data-ttu-id="03791-110">Az egységes Oracle $A $, amely előkészíti a kiegészítő indítási állapotot</span><span class="sxs-lookup"><span data-stu-id="03791-110">Unitary oracle $A$ that prepares auxiliary start state</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="03791-111">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="03791-111">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="03791-112">Egységes Oracle $O $ típusú, `ObliviousOracle` amely közösen működik a kiegészítő és a rendszerregisztráción</span><span class="sxs-lookup"><span data-stu-id="03791-112">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system register</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="03791-113">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="03791-113">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="03791-114">Index – qubit jelző regisztrálása</span><span class="sxs-lookup"><span data-stu-id="03791-114">Index to single-qubit flag register</span></span>



## <a name="output--qubitqubit--unit-adj--ctl"></a><span data-ttu-id="03791-115">Kimenet: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="03791-115">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="03791-116">Egy művelet, amely a részleges reflexiók alapján elismeri az amplitúdó-erősítést.</span><span class="sxs-lookup"><span data-stu-id="03791-116">An operation that implements oblivious amplitude amplification based on partial reflections.</span></span>

## <a name="remarks"></a><span data-ttu-id="03791-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="03791-117">Remarks</span></span>

<span data-ttu-id="03791-118">Ez szigorúbb feltételeket ró a kisegítő kezdő és megcélzott állapotok formájára, mint a-ben `AmpAmpObliviousByReflectionPhases` .</span><span class="sxs-lookup"><span data-stu-id="03791-118">This imposes stricter conditions on form of the auxiliary start and target states than in `AmpAmpObliviousByReflectionPhases`.</span></span>
<span data-ttu-id="03791-119">Feltételezzük, hogy $A \ket {0} \_ f\ket {0} \_ a = \ket{\text{Start}} \_ {fa} $ előkészíti a kiegészítő indítási állapotot $ \ket{\text{Start}} \_ {fa} $-re a számítási alap $ \ket {0} \_ f\ket {0} $ értékről.</span><span class="sxs-lookup"><span data-stu-id="03791-119">It is assumed that $A\ket{0}\_f\ket{0}\_a= \ket{\text{start}}\_{fa}$ prepares the auxiliary start state $\ket{\text{start}}\_{fa}$ from the computational basis $\ket{0}\_f\ket{0}$.</span></span>
<span data-ttu-id="03791-120">Feltételezzük, hogy a megcélzott állapotot $ \ket f $ jelöléssel jelölte meg {1} \_ .</span><span class="sxs-lookup"><span data-stu-id="03791-120">It is assumed that the target state is marked by $\ket{1}\_f$.</span></span>
<span data-ttu-id="03791-121">Feltételezzük, hogy a \begin{align} O\ket {\ Text {Start}} \_ {fa} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ Text {Anything}} \_ a\ket {\ Text {Target}} \_ s U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} egyes egységes $U $-hoz.</span><span class="sxs-lookup"><span data-stu-id="03791-121">It is assumed that \begin{align} O\ket{\text{start}}\_{fa}\ket{\psi}\_s= \lambda\ket{1}\_f\ket{\text{anything}}\_a\ket{\text{target}}\_s U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} for some unitary $U$.</span></span>