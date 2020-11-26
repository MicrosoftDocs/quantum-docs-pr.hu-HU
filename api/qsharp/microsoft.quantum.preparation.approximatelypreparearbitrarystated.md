---
uid: Microsoft.Quantum.Preparation.ApproximatelyPrepareArbitraryStateD
title: ApproximatelyPrepareArbitraryStateD művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: ApproximatelyPrepareArbitraryStateD
qsharp.summary: Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.
ms.openlocfilehash: 822efe08e66c43b7a3128d100e3e58a8c2ce3c2e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193590"
---
# <a name="approximatelypreparearbitrarystated-operation"></a><span data-ttu-id="f0fce-102">ApproximatelyPrepareArbitraryStateD művelet</span><span class="sxs-lookup"><span data-stu-id="f0fce-102">ApproximatelyPrepareArbitraryStateD operation</span></span>

<span data-ttu-id="f0fce-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="f0fce-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="f0fce-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f0fce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f0fce-105">Az együtthatók halmaza és a endian kódolt kvantum-regisztrációja miatt az adott, a megadott együtthatók által ismertetett regiszteren alapuló állapotot készít elő, amely egy adott közelítési toleranciára vonatkozik.</span><span class="sxs-lookup"><span data-stu-id="f0fce-105">Given a set of coefficients and a little-endian encoded quantum register, prepares an state on that register described by the given coefficients, up to a given approximation tolerance.</span></span>

```qsharp
operation ApproximatelyPrepareArbitraryStateD (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="f0fce-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="f0fce-106">Description</span></span>

<span data-ttu-id="f0fce-107">Ez a művelet előkészít egy tetszőleges kvantum-állapotot ($ \ket{\psi} $) összetett együtthatókkal $r _j e ^ {i t_j} $ értéket a $n $ qubit számítási \ket{0 \cdots 0} $ értékről.</span><span class="sxs-lookup"><span data-stu-id="f0fce-107">This operation prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0 \cdots 0}$.</span></span>
<span data-ttu-id="f0fce-108">Különösen a művelet műveletét szimulálhatja egy egységes átalakítással $U $, amely az összes nulla állapotot használja</span><span class="sxs-lookup"><span data-stu-id="f0fce-108">In particular, the action of this operation can be simulated by the a unitary transformation $U$ which acts on the all-zeros state as</span></span>

<span data-ttu-id="f0fce-109">$ $ \begin{align} U\ket {0... 0} & = \ket{\psi} \\ \\ & = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}} {\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="f0fce-109">$$ \begin{align} U\ket{0...0} & = \ket{\psi} \\\\ & = \frac{ \sum_{j=0}^{2^n-1} r_j e^{i t_j} \ket{j} }{ \sqrt{\sum_{j=0}^{2^n-1} |r_j|^2} }.</span></span>
<span data-ttu-id="f0fce-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="f0fce-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="f0fce-111">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f0fce-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="f0fce-112">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f0fce-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f0fce-113">A megadott állapot előkészítésekor használandó közelítési tűréshatár.</span><span class="sxs-lookup"><span data-stu-id="f0fce-113">The approximation tolerance to be used when preparing the given state.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="f0fce-114">együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f0fce-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f0fce-115">Legfeljebb $2 ^ n $ valódi együtthatók tömbje.</span><span class="sxs-lookup"><span data-stu-id="f0fce-115">Array of up to $2^n$ real coefficients.</span></span> <span data-ttu-id="f0fce-116">A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.</span><span class="sxs-lookup"><span data-stu-id="f0fce-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="f0fce-117">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f0fce-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f0fce-118">A Qubit endian formátumban regisztrálja a kódolási számokat.</span><span class="sxs-lookup"><span data-stu-id="f0fce-118">Qubit register encoding number states in little-endian format.</span></span> <span data-ttu-id="f0fce-119">Ezt a rendszer a számítási alapon a $ \ket{0...0} $ értékkel inicializálja.</span><span class="sxs-lookup"><span data-stu-id="f0fce-119">This is expected to be initialized in the computational basis state $\ket{0...0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f0fce-120">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f0fce-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="f0fce-121">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="f0fce-121">Remarks</span></span>

<span data-ttu-id="f0fce-122">A negatív bemeneti együtthatók $r _j < $0-as értéke pozitív a $ | r_j | $ értékkel.</span><span class="sxs-lookup"><span data-stu-id="f0fce-122">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="f0fce-123">`coefficients` a (r_j, t_j) = (0,0, 0,0) $ értékkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.</span><span class="sxs-lookup"><span data-stu-id="f0fce-123">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="f0fce-124">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="f0fce-124">References</span></span>

- <span data-ttu-id="f0fce-125">A kvantum-logikai áramkörök összeszintézise: Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="f0fce-125">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>