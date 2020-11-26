---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: ApplyObliviousAmplitudeAmplification művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: 9b0060201bcdae02a207362a753a0a403cdbb896
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191516"
---
# <a name="applyobliviousamplitudeamplification-operation"></a><span data-ttu-id="4cb6d-102">ApplyObliviousAmplitudeAmplification művelet</span><span class="sxs-lookup"><span data-stu-id="4cb6d-102">ApplyObliviousAmplitudeAmplification operation</span></span>

<span data-ttu-id="4cb6d-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="4cb6d-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="4cb6d-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4cb6d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4cb6d-105">A részleges reflexiók megadásával megfeledkezett az amplitúdó-erősítésről.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-105">Oblivious amplitude amplification by specifying partial reflections.</span></span>

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4cb6d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4cb6d-106">Input</span></span>

### <a name="phases--reflectionphases"></a><span data-ttu-id="4cb6d-107">fázisok: [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span><span class="sxs-lookup"><span data-stu-id="4cb6d-107">phases : [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)</span></span>

<span data-ttu-id="4cb6d-108">Részleges tükrözések fázisai</span><span class="sxs-lookup"><span data-stu-id="4cb6d-108">Phases of partial reflections</span></span>


### <a name="startstatereflection--reflectionoracle"></a><span data-ttu-id="4cb6d-109">startStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="4cb6d-109">startStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="4cb6d-110">A kiegészítő regisztráció indítási állapotával kapcsolatos reflexiós operátor</span><span class="sxs-lookup"><span data-stu-id="4cb6d-110">Reflection operator about start state of auxiliary register</span></span>


### <a name="targetstatereflection--reflectionoracle"></a><span data-ttu-id="4cb6d-111">targetStateReflection: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span><span class="sxs-lookup"><span data-stu-id="4cb6d-111">targetStateReflection : [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)</span></span>

<span data-ttu-id="4cb6d-112">A kiegészítő regiszter megcélzott állapotával kapcsolatos reflexiós operátor</span><span class="sxs-lookup"><span data-stu-id="4cb6d-112">Reflection operator about target state of auxiliary register</span></span>


### <a name="signaloracle--obliviousoracle"></a><span data-ttu-id="4cb6d-113">signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span><span class="sxs-lookup"><span data-stu-id="4cb6d-113">signalOracle : [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)</span></span>

<span data-ttu-id="4cb6d-114">Egységes Oracle $O $ típusú, `ObliviousOracle` amely közösen működik a kiegészítő és a rendszerregisztrálók esetében.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-114">Unitary oracle $O$ of type `ObliviousOracle` that acts jointly on the auxiliary and system registers.</span></span>


### <a name="auxiliaryregister--qubit"></a><span data-ttu-id="4cb6d-115">auxiliaryRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4cb6d-115">auxiliaryRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4cb6d-116">Kiegészítő regisztráció</span><span class="sxs-lookup"><span data-stu-id="4cb6d-116">Auxiliary register</span></span>


### <a name="systemregister--qubit"></a><span data-ttu-id="4cb6d-117">systemRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4cb6d-117">systemRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4cb6d-118">Rendszerregisztráció</span><span class="sxs-lookup"><span data-stu-id="4cb6d-118">System register</span></span>



## <a name="output--unit"></a><span data-ttu-id="4cb6d-119">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4cb6d-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4cb6d-120">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="4cb6d-120">Remarks</span></span>

<span data-ttu-id="4cb6d-121">Egy adott kiegészítő indítási állapothoz $ \ket{\text{Start}} \_ a $, egy adott kiegészítő megcélzott állapot $ \ket{\text{Target}} $ \_ és minden rendszerállapot $ \ket{\psi} \_ s $, tegyük fel, hogy a \begin{align} O\ket {\ Text {Start}} \_ a\ket {\ PSI} \_ s = \lambda\ket{\text{Target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\text{target} ^ \perp} \_ a\cdots \end{align} néhány egységes $U $.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-121">Given a particular auxiliary start state $\ket{\text{start}}\_a$, a particular auxiliary target state $\ket{\text{target}}\_a$, and any system state $\ket{\psi}\_s$, suppose that \begin{align} O\ket{\text{start}}\_a\ket{\psi}\_s= \lambda\ket{\text{target}}\_a U \ket{\psi}\_s + \sqrt{1-|\lambda|^2}\ket{\text{target}^\perp}\_a\cdots \end{align} for some unitary $U$.</span></span>
<span data-ttu-id="4cb6d-122">A kezdő és a cél állapotokra vonatkozó, az alkalmazások és a adjoint által összekapcsolt kiegészítő regisztráció során felmerülő reflexiók sorozatából az `signalOracle` U alkalmazásának sikerességi valószínűsége módosítható.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-122">By a sequence of reflections about the start and target states on the auxiliary register interleaved by applications of `signalOracle` and its adjoint, the success probability of applying U may be altered.</span></span>

<span data-ttu-id="4cb6d-123">A legtöbb esetben `auxiliaryRegister` a a $ \ket{\text{Start}} állapotban van inicializálva \_ .</span><span class="sxs-lookup"><span data-stu-id="4cb6d-123">In most cases, `auxiliaryRegister` is initialized in the state $\ket{\text{start}}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="4cb6d-124">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="4cb6d-124">References</span></span>

<span data-ttu-id="4cb6d-125">Lásd:</span><span class="sxs-lookup"><span data-stu-id="4cb6d-125">See</span></span>

- <span data-ttu-id="4cb6d-126">[ *DW Berry, am Childs, r. Cleve, r. Kothari, R.D. Somma*](https://arxiv.org/abs/1312.1414) a standard verzióhoz.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-126">[ *D.W. Berry, A.M. Childs, R. Cleve, R. Kothari, R.D. Somma* ](https://arxiv.org/abs/1312.1414) for the standard version.</span></span>
  <span data-ttu-id="4cb6d-127">Lásd:</span><span class="sxs-lookup"><span data-stu-id="4cb6d-127">See</span></span>
- <span data-ttu-id="4cb6d-128">[ *Alacsony G.H., I.L.*](https://arxiv.org/abs/1610.06546) a részleges tükrözések általánosításához.</span><span class="sxs-lookup"><span data-stu-id="4cb6d-128">[ *G.H. Low, I.L. Chuang* ](https://arxiv.org/abs/1610.06546) for a generalization to partial reflections.</span></span>