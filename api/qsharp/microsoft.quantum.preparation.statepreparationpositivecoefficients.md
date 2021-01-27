---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients függvény
ms.date: 1/23/2021 12:00:00 AM
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
ms.openlocfilehash: 081541d93bf853fa0de1573038dc00c296432281
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855845"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="dfaf7-102">StatePreparationPositiveCoefficients függvény</span><span class="sxs-lookup"><span data-stu-id="dfaf7-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="dfaf7-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="dfaf7-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="dfaf7-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dfaf7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="dfaf7-105">A StatePreparationPositiveCoefficients elavult.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-105">StatePreparationPositiveCoefficients has been deprecated.</span></span> <span data-ttu-id="dfaf7-106">Használja <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> helyette.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateD> instead.</span></span>

<span data-ttu-id="dfaf7-107">Egy olyan műveletet ad vissza, amely előkészíti a megadott kvantum-állapotot.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-107">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="dfaf7-108">A visszaadott művelet $U $ előkészít egy tetszőleges kvantum-állapotot ($ \ket{\psi} $) a következő pozitív együtthatókkal: $ \ alpha_j \ge $0 az $n $-qubit számítási alapja $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="dfaf7-109">Az U művelet az újonnan lefoglalt regisztrációhoz $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-109">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="dfaf7-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="dfaf7-110">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="dfaf7-111">Bevitel</span><span class="sxs-lookup"><span data-stu-id="dfaf7-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="dfaf7-112">együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="dfaf7-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="dfaf7-113">Legfeljebb $2 ^ n $ együttható, $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-113">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="dfaf7-114">A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="dfaf7-115">Kimenet: az [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="dfaf7-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="dfaf7-116">Az állapot-előkészítési egységes művelet $U $.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-116">A state-preparation unitary operation $U$.</span></span>

## <a name="example"></a><span data-ttu-id="dfaf7-117">Példa</span><span class="sxs-lookup"><span data-stu-id="dfaf7-117">Example</span></span>

<span data-ttu-id="dfaf7-118">A következő kódrészlet előkészíti a Quantum State $ \ket{\psi} = \ SQRT {1/8} \ ket {0} + \ SQRT {7/8} \ ket {2} $ értéket a qubit-regisztrációban `qubitsLE` .</span><span class="sxs-lookup"><span data-stu-id="dfaf7-118">The following snippet prepares the quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{2}$ in the qubit register `qubitsLE`.</span></span>

```qsharp
let amplitudes = [Sqrt(0.125), 0.0, Sqrt(0.875), 0.0];
let op = StatePreparationPositiveCoefficients(amplitudes);
using (qubits = Qubit[2]) {
    let qubitsLE = LittleEndian(qubits);
    op(qubitsLE);
}
```

## <a name="remarks"></a><span data-ttu-id="dfaf7-119">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="dfaf7-119">Remarks</span></span>

<span data-ttu-id="dfaf7-120">A negatív bemeneti együtthatók $ \ alpha_j < $0 a (z) $ | \ alpha_j | $ értékű pozitív értékkel lesznek kezelve.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-120">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="dfaf7-121">`coefficients` a $ \ alpha_j = $0,0 elemekkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.</span><span class="sxs-lookup"><span data-stu-id="dfaf7-121">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>