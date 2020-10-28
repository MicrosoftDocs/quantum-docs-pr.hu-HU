---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: StandardAmplitudeAmplification függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 18228d45c4df280b004c595a7b0f1e2a607b8b2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721750"
---
# <a name="standardamplitudeamplification-function"></a><span data-ttu-id="b98a4-102">StandardAmplitudeAmplification függvény</span><span class="sxs-lookup"><span data-stu-id="b98a4-102">StandardAmplitudeAmplification function</span></span>

<span data-ttu-id="b98a4-103">Névtér: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="b98a4-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="b98a4-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b98a4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b98a4-105">Standard amplitúdó-erősítési algoritmus</span><span class="sxs-lookup"><span data-stu-id="b98a4-105">Standard Amplitude Amplification algorithm</span></span>

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="b98a4-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b98a4-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="b98a4-107">nIterations: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b98a4-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b98a4-108">Ismétlések száma $n $ amplitúdó-erősítéssel</span><span class="sxs-lookup"><span data-stu-id="b98a4-108">Number of iterations $n$ of amplitude amplification</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="b98a4-109">stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="b98a4-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="b98a4-110">Az egységes Oracle $A $, amely előkészíti az indítási állapotot</span><span class="sxs-lookup"><span data-stu-id="b98a4-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="b98a4-111">idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b98a4-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b98a4-112">Index a qubit jelzőhöz</span><span class="sxs-lookup"><span data-stu-id="b98a4-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="b98a4-113">Kimenet: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="b98a4-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="b98a4-114">A standard amplitúdó-erősítési kvantum-algoritmust megvalósító művelet</span><span class="sxs-lookup"><span data-stu-id="b98a4-114">An operation that implements the standard amplitude amplification quantum algorithm</span></span>

## <a name="remarks"></a><span data-ttu-id="b98a4-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b98a4-115">Remarks</span></span>

<span data-ttu-id="b98a4-116">Ez a szabványos amplitúdó-erősítési algoritmus, amely a kiszámított gondolkodási fázisok alapján lett kiszámítva `AmpAmpPhasesStandard` , feltételezve, hogy a \Begin{align} A\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ Text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots, \end{align} ez a művelet előkészíti a \begin{align} \operatorname{AmpAmpByOracle}\ket {0} \_ {f} \ket {0} \_ s = \sin ((2n + 1) \sin ^ {-1} (\lambda)) \ket f\ket {1} \_ {\ Text {Target}} \_ s + \cdots\ket {0} \_ f \end{align} a legtöbb esetben, `flagQubit` és `auxiliaryRegister` inicializálása a {0} \_ $ \ket f\ket {0} \_ a $ értékkel történik.</span><span class="sxs-lookup"><span data-stu-id="b98a4-116">This is the standard amplitude amplification algorithm obtained by a choice of reflection phases computed by `AmpAmpPhasesStandard` Assuming that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} this operation prepares the state \begin{align} \operatorname{AmpAmpByOracle}\ket{0}\_{f}\ket{0}\_s= \sin((2n+1)\sin^{-1}(\lambda))\ket{1}\_f\ket{\text{target}}\_s + \cdots\ket{0}\_f \end{align} In most cases, `flagQubit` and `auxiliaryRegister` is initialized in the state $\ket{0}\_f\ket{0}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="b98a4-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="b98a4-117">References</span></span>

- [<span data-ttu-id="b98a4-118">*G. Brassard, P. Hoyer, M. Mosca, A. menetfúró*</span><span class="sxs-lookup"><span data-stu-id="b98a4-118"> *G. Brassard, P. Hoyer, M. Mosca, A. Tapp* </span></span>](https://arxiv.org/abs/quant-ph/0005055)