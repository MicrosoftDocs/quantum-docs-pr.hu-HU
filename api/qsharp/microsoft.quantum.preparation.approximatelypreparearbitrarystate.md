---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState
title: ApproximatelyPrepareArbitraryState művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryState
qsharp.summary: >-
  > [!WARNING]

  > ApproximatelyPrepareArbitraryState has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP> instead.


  Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 9e1b172258acd0cb09b824a773e7e79d44fec20c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193709"
---
# <a name="approximatelypreparearbitrarystate-operation"></a><span data-ttu-id="f141f-102">ApproximatelyPrepareArbitraryState művelet</span><span class="sxs-lookup"><span data-stu-id="f141f-102">ApproximatelyPrepareArbitraryState operation</span></span>

<span data-ttu-id="f141f-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f141f-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f141f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f141f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="f141f-105">A ApproximatelyPrepareArbitraryState elavult.</span><span class="sxs-lookup"><span data-stu-id="f141f-105">ApproximatelyPrepareArbitraryState has been deprecated.</span></span> <span data-ttu-id="f141f-106">Használja <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP> helyette.</span><span class="sxs-lookup"><span data-stu-id="f141f-106">Please use <xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="f141f-107">Az együtthatók halmaza és a endian kódolt kvantum-regisztrációja miatt az adott, a megadott együtthatók által ismertetett regiszteren alapuló állapotot készít elő, amely egy adott közelítési toleranciára vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="f141f-107">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryState (tolerance : Double, coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f141f-108">Leírás</span><span class="sxs-lookup"><span data-stu-id="f141f-108">Description</span></span>

<span data-ttu-id="f141f-109">Ez a művelet előkészít egy tetszőleges kvantum-állapotot ($ \ket{\psi} $) összetett együtthatókkal $r _j e ^ {i t_j} $ értéket a $n $ qubit számítási \ket{0 \cdots 0} $ értékről.</span><span class="sxs-lookup"><span data-stu-id="f141f-109">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="f141f-110">Különösen a művelet műveletét szimulálhatja egy egységes átalakítással $U $, amely az összes nulla állapotot használja</span><span class="sxs-lookup"><span data-stu-id="f141f-110">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="f141f-111">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="f141f-111">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="f141f-112">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="f141f-112">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="f141f-113">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f141f-113">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="f141f-114">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f141f-114">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f141f-115">A megadott állapot előkészítésekor használandó közelítési tűréshatár.</span><span class="sxs-lookup"><span data-stu-id="f141f-115">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--complexpolar"></a><span data-ttu-id="f141f-116">együtthatók: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="f141f-116">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="f141f-117">Legfeljebb $2 ^ n $ összetett együtthatók, amelyek abszolút értéke és a $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="f141f-117">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="f141f-118">A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.</span><span class="sxs-lookup"><span data-stu-id="f141f-118">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="f141f-119">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f141f-119">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f141f-120">A Qubit endian formátumban regisztrálja a kódolási számokat.</span><span class="sxs-lookup"><span data-stu-id="f141f-120">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="f141f-121">Ezt a rendszer a számítási alapon a $ \ket{0...0} $ értékkel inicializálja.</span><span class="sxs-lookup"><span data-stu-id="f141f-121">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f141f-122">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f141f-122">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f141f-123">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="f141f-123">Remarks</span></span>

<span data-ttu-id="f141f-124">A negatív bemeneti együtthatók $r _j < $0-as értéke pozitív a $ | r_j | $ értékkel.</span><span class="sxs-lookup"><span data-stu-id="f141f-124">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="f141f-125">`coefficients` a (r_j, t_j) = (0,0, 0,0) $ értékkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.</span><span class="sxs-lookup"><span data-stu-id="f141f-125">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="f141f-126">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="f141f-126">References</span></span>

- <span data-ttu-id="f141f-127">A kvantum-logikai áramkörök összeszintézise: Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="f141f-127">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="f141f-128">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="f141f-128">See Also</span></span>

- [<span data-ttu-id="f141f-129">Microsoft. Quantum. előkészítés. ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="f141f-129">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)