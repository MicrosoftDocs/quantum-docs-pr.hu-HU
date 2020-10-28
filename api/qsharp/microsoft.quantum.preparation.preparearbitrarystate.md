---
uid: Microsoft.Quantum.Preparation.PrepareArbitraryState
title: PrepareArbitraryState művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareArbitraryState
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.
ms.openlocfilehash: 18f45da601b02fc5f83936b086323e31a66fc20b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724046"
---
# <a name="preparearbitrarystate-operation"></a><span data-ttu-id="117ff-102">PrepareArbitraryState művelet</span><span class="sxs-lookup"><span data-stu-id="117ff-102">PrepareArbitraryState operation</span></span>

<span data-ttu-id="117ff-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="117ff-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="117ff-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="117ff-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="117ff-105">Az egyes együtthatók és egy kis endian kódolt kvantum-regisztráció miatt a rendszer előkészíti az adott regiszteren belüli olyan állapotot, amelyet a megadott együtthatók ismertetnek.</span><span class="sxs-lookup"><span data-stu-id="117ff-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients.</span></span>

```qsharp
operation PrepareArbitraryState (coefficients : Microsoft.Quantum.Math.ComplexPolar[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="117ff-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="117ff-106">Description</span></span>

<span data-ttu-id="117ff-107">Ez a művelet előkészít egy tetszőleges kvantum-állapotot ($ \ket{\psi} $) összetett együtthatókkal $r _j e ^ {i t_j} $ értéket a $n $ qubit számítási \ket{0 \cdots 0} $ értékről.</span><span class="sxs-lookup"><span data-stu-id="117ff-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="117ff-108">Különösen a művelet műveletét szimulálhatja egy egységes átalakítással $U $, amely az összes nulla állapotot használja</span><span class="sxs-lookup"><span data-stu-id="117ff-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="117ff-109">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="117ff-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="117ff-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="117ff-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="117ff-111">Bevitel</span><span class="sxs-lookup"><span data-stu-id="117ff-111">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="117ff-112">együtthatók: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="117ff-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="117ff-113">Legfeljebb $2 ^ n $ összetett együtthatók, amelyek abszolút értéke és a $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="117ff-113">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="117ff-114">A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.</span><span class="sxs-lookup"><span data-stu-id="117ff-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="117ff-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="117ff-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="117ff-116">A Qubit endian formátumban regisztrálja a kódolási számokat.</span><span class="sxs-lookup"><span data-stu-id="117ff-116">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="117ff-117">Ezt a rendszer a számítási alapon a $ \ket{0...0} $ értékkel inicializálja.</span><span class="sxs-lookup"><span data-stu-id="117ff-117">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="117ff-118">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="117ff-118">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="117ff-119">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="117ff-119">Remarks</span></span>

<span data-ttu-id="117ff-120">A negatív bemeneti együtthatók $r _j < $0-as értéke pozitív a $ | r_j | $ értékkel.</span><span class="sxs-lookup"><span data-stu-id="117ff-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="117ff-121">`coefficients` a (r_j, t_j) = (0,0, 0,0) $ értékkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.</span><span class="sxs-lookup"><span data-stu-id="117ff-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="117ff-122">Referencia</span><span class="sxs-lookup"><span data-stu-id="117ff-122">References</span></span>

- <span data-ttu-id="117ff-123">A kvantum-logikai áramkörök összeszintézise: Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="117ff-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="117ff-124">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="117ff-124">See Also</span></span>

- [<span data-ttu-id="117ff-125">Microsoft. Quantum. előkészítés. ApproximatelyPrepareArbitraryState</span><span class="sxs-lookup"><span data-stu-id="117ff-125">Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState</span></span>](xref:Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryState)