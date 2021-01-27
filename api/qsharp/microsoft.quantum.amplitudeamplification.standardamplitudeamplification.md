---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: StandardAmplitudeAmplification függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 984bfee89b6d79750228b8ca6aaf404f58aecd41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843935"
---
# <a name="standardamplitudeamplification-function"></a><span data-ttu-id="e582a-102">StandardAmplitudeAmplification függvény</span><span class="sxs-lookup"><span data-stu-id="e582a-102">StandardAmplitudeAmplification function</span></span>

<span data-ttu-id="e582a-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="e582a-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="e582a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e582a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e582a-105">Standard amplitúdó-erősítési algoritmus</span><span class="sxs-lookup"><span data-stu-id="e582a-105">Standard Amplitude Amplification algorithm</span></span>

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="e582a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e582a-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="e582a-107">nIterations: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e582a-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e582a-108">Ismétlések száma $n $ amplitúdó-erősítéssel</span><span class="sxs-lookup"><span data-stu-id="e582a-108">Number of iterations $n$ of amplitude amplification</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="e582a-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="e582a-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="e582a-110">Az egységes Oracle $A $, amely előkészíti az indítási állapotot</span><span class="sxs-lookup"><span data-stu-id="e582a-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="e582a-111">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e582a-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e582a-112">Index a qubit jelzőhöz</span><span class="sxs-lookup"><span data-stu-id="e582a-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit--is-adj--ctl"></a><span data-ttu-id="e582a-113">Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="e582a-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="e582a-114">A standard amplitúdó-erősítési kvantum-algoritmust megvalósító művelet</span><span class="sxs-lookup"><span data-stu-id="e582a-114">An operation that implements the standard amplitude amplification quantum algorithm</span></span>

## <a name="remarks"></a><span data-ttu-id="e582a-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="e582a-115">Remarks</span></span>

<span data-ttu-id="e582a-116">Ez a szabványos amplitúdó-erősítési algoritmus, amely a kiszámított gondolkodási fázisok alapján lett kiszámítva `AmpAmpPhasesStandard` , feltételezve, hogy a \Begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ Text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} ez a művelet előkészíti a \begin{align} \operatorname{AmpAmpByOracle}\ket {0} \_ {f} \ket {0} \_ s = \sin ((2n + 1) \sin ^ {-1} (\lambda)) \ket f\ket {1} \_ {\ Text {Target}} \_ s + \cdots\ket {0} \_ f \end{align} a legtöbb esetben, `flagQubit` és `auxiliaryRegister` inicializálása a {0} \_ $ \ket f\ket {0} \_ a $ értékkel történik.</span><span class="sxs-lookup"><span data-stu-id="e582a-116">This is the standard amplitude amplification algorithm obtained by a choice of reflection phases computed by `AmpAmpPhasesStandard` Assuming that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} this operation prepares the state \begin{align} \operatorname{AmpAmpByOracle}\ket{0}\_{f}\ket{0}\_s= \sin((2n+1)\sin^{-1}(\lambda))\ket{1}\_f\ket{\text{target}}\_s + \cdots\ket{0}\_f \end{align} In most cases, `flagQubit` and `auxiliaryRegister` is initialized in the state $\ket{0}\_f\ket{0}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="e582a-117">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="e582a-117">References</span></span>

- [<span data-ttu-id="e582a-118">*G. Brassard, P. Hoyer, M. Mosca, A. menetfúró*</span><span class="sxs-lookup"><span data-stu-id="e582a-118"> *G. Brassard, P. Hoyer, M. Mosca, A. Tapp* </span></span>](https://arxiv.org/abs/quant-ph/0005055)