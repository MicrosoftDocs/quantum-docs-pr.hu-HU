---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState
title: ApproximatelyPrepareArbitraryState művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 2561b098c5faf2d24bb9ab348fb052025808e441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724088"
---
# <a name="approximatelypreparearbitrarystate-operation"></a><span data-ttu-id="5083c-102">ApproximatelyPrepareArbitraryState művelet</span><span class="sxs-lookup"><span data-stu-id="5083c-102">ApproximatelyPrepareArbitraryState operation</span></span>

<span data-ttu-id="5083c-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="5083c-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="5083c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5083c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5083c-105">Az együtthatók halmaza és a endian kódolt kvantum-regisztrációja miatt az adott, a megadott együtthatók által ismertetett regiszteren alapuló állapotot készít elő, amely egy adott közelítési toleranciára vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="5083c-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryState (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="5083c-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="5083c-106">Description</span></span>

<span data-ttu-id="5083c-107">Ez a művelet előkészít egy tetszőleges kvantum-állapotot ($ \ket{\psi} $) összetett együtthatókkal $r _j e ^ {i t_j} $ értéket a $n $ qubit számítási \ket{0 \cdots 0} $ értékről.</span><span class="sxs-lookup"><span data-stu-id="5083c-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="5083c-108">Különösen a művelet műveletét szimulálhatja egy egységes átalakítással $U $, amely az összes nulla állapotot használja</span><span class="sxs-lookup"><span data-stu-id="5083c-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="5083c-109">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="5083c-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="5083c-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="5083c-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="5083c-111">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5083c-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="5083c-112">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5083c-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5083c-113">A megadott állapot előkészítésekor használandó közelítési tűréshatár.</span><span class="sxs-lookup"><span data-stu-id="5083c-113">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--complexpolar"></a><span data-ttu-id="5083c-114">együtthatók: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="5083c-114">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="5083c-115">Legfeljebb $2 ^ n $ összetett együtthatók, amelyek abszolút értéke és a $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="5083c-115">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="5083c-116">A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.</span><span class="sxs-lookup"><span data-stu-id="5083c-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="5083c-117">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5083c-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5083c-118">A Qubit endian formátumban regisztrálja a kódolási számokat.</span><span class="sxs-lookup"><span data-stu-id="5083c-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="5083c-119">Ezt a rendszer a számítási alapon a $ \ket{0...0} $ értékkel inicializálja.</span><span class="sxs-lookup"><span data-stu-id="5083c-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5083c-120">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5083c-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5083c-121">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="5083c-121">Remarks</span></span>

<span data-ttu-id="5083c-122">A negatív bemeneti együtthatók $r _j < $0-as értéke pozitív a $ | r_j | $ értékkel.</span><span class="sxs-lookup"><span data-stu-id="5083c-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="5083c-123">`coefficients` a (r_j, t_j) = (0,0, 0,0) $ értékkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.</span><span class="sxs-lookup"><span data-stu-id="5083c-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="5083c-124">Referencia</span><span class="sxs-lookup"><span data-stu-id="5083c-124">References</span></span>

- <span data-ttu-id="5083c-125">A kvantum-logikai áramkörök összeszintézise: Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="5083c-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="5083c-126">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="5083c-126">See Also</span></span>

- [<span data-ttu-id="5083c-127">Microsoft. Quantum. előkészítés. ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="5083c-127">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)