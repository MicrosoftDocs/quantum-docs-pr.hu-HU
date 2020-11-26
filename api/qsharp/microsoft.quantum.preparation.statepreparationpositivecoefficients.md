---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationPositiveCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.


  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 8f1fd7d77531996faf566adb78f452929d6cbd50
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193250"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="68ed4-102">StatePreparationPositiveCoefficients függvény</span><span class="sxs-lookup"><span data-stu-id="68ed4-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="68ed4-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="68ed4-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="68ed4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="68ed4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="68ed4-105">A StatePreparationPositiveCoefficients elavult.</span><span class="sxs-lookup"><span data-stu-id="68ed4-105">StatePreparationPositiveCoefficients has been deprecated.</span></span> <span data-ttu-id="68ed4-106">Használja <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> helyette.</span><span class="sxs-lookup"><span data-stu-id="68ed4-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.</span></span>

<span data-ttu-id="68ed4-107">Egy olyan műveletet ad vissza, amely előkészíti a megadott kvantum-állapotot.</span><span class="sxs-lookup"><span data-stu-id="68ed4-107">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="68ed4-108">A visszaadott művelet $U $ előkészít egy tetszőleges kvantum-állapotot ($ \ket{\psi} $) a következő pozitív együtthatókkal: $ \ alpha_j \ge $0 az $n $-qubit számítási alapja $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="68ed4-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="68ed4-109">Az U művelet az újonnan lefoglalt regisztrációhoz $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="68ed4-109">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="68ed4-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="68ed4-110">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="68ed4-111">Bevitel</span><span class="sxs-lookup"><span data-stu-id="68ed4-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="68ed4-112">együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="68ed4-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="68ed4-113">Legfeljebb $2 ^ n $ együttható, $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="68ed4-113">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="68ed4-114">A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.</span><span class="sxs-lookup"><span data-stu-id="68ed4-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="68ed4-115">Kimenet: az [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="68ed4-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="68ed4-116">Az állapot-előkészítési egységes művelet $U $.</span><span class="sxs-lookup"><span data-stu-id="68ed4-116">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="68ed4-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="68ed4-117">Remarks</span></span>

<span data-ttu-id="68ed4-118">A negatív bemeneti együtthatók $ \ alpha_j < $0 a (z) $ | \ alpha_j | $ értékű pozitív értékkel lesznek kezelve.</span><span class="sxs-lookup"><span data-stu-id="68ed4-118">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="68ed4-119">`coefficients` a $ \ alpha_j = $0,0 elemekkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.</span><span class="sxs-lookup"><span data-stu-id="68ed4-119">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>