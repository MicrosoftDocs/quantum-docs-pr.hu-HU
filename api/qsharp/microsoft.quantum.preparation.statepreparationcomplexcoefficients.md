---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  > [!WARNING]

  > StatePreparationComplexCoefficients has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.


  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: c16df0fe075b15cff745a6b7d5b79aac39c14d09
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856135"
---
# <a name="statepreparationcomplexcoefficients-function"></a><span data-ttu-id="23493-102">StatePreparationComplexCoefficients függvény</span><span class="sxs-lookup"><span data-stu-id="23493-102">StatePreparationComplexCoefficients function</span></span>

<span data-ttu-id="23493-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="23493-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="23493-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="23493-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="23493-105">A StatePreparationComplexCoefficients elavult.</span><span class="sxs-lookup"><span data-stu-id="23493-105">StatePreparationComplexCoefficients has been deprecated.</span></span> <span data-ttu-id="23493-106">Használja <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> helyette.</span><span class="sxs-lookup"><span data-stu-id="23493-106">Please use <xref:Microsoft.Quantum.Preparation.PrepareArbitraryStateCP> instead.</span></span>

<span data-ttu-id="23493-107">Egy olyan műveletet ad vissza, amely egy adott kvantum-állapotot készít elő.</span><span class="sxs-lookup"><span data-stu-id="23493-107">Returns an operation that prepares a specific quantum state.</span></span>

<span data-ttu-id="23493-108">A visszaadott művelet $U $ felkészít egy tetszőleges kvantum-állapotot ($ \ket{\psi} $) összetett együtthatókkal $r _j e ^ {i t_j} $ értéket a $n $ qubit számítási alapból $ \ket{0...0} $ értékre.</span><span class="sxs-lookup"><span data-stu-id="23493-108">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="23493-109">Az U egy újonnan lefoglalt regisztrációra vonatkozó műveletét $ $ \begin{align} U\ket {0... 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="23493-109">The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}.</span></span>
<span data-ttu-id="23493-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="23493-110">\end{align} $$</span></span>

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="23493-111">Bevitel</span><span class="sxs-lookup"><span data-stu-id="23493-111">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="23493-112">együtthatók: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="23493-112">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="23493-113">Legfeljebb $2 ^ n $ összetett együtthatók, amelyek abszolút értéke és a $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="23493-113">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="23493-114">A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.</span><span class="sxs-lookup"><span data-stu-id="23493-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit--is-adj--ctl"></a><span data-ttu-id="23493-115">Kimenet: az [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="23493-115">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="23493-116">Az állapot-előkészítési egységes művelet $U $.</span><span class="sxs-lookup"><span data-stu-id="23493-116">A state-preparation unitary operation $U$.</span></span>

## <a name="example"></a><span data-ttu-id="23493-117">Példa</span><span class="sxs-lookup"><span data-stu-id="23493-117">Example</span></span>

<span data-ttu-id="23493-118">A következő kódrészlet előkészíti a kvantum-állapotot: $ \ket{\psi} = e ^ {i 0.1} \ SQRT {1/8} \ ket {0} + \ SQRT {7/8} \ ket {2} $ a qubit-regisztrációban `qubitsLE` .</span><span class="sxs-lookup"><span data-stu-id="23493-118">The following snippet prepares the quantum state $\ket{\psi}=e^{i 0.1}\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{2}$ in the qubit register `qubitsLE`.</span></span>

```qsharp
let amplitudes = [Sqrt(0.125), 0.0, Sqrt(0.875), 0.0];
let phases = [0.1, 0.0, 0.0, 0.0];
mutable complexNumbers = new ComplexPolar[4];
for (idx in 0..3) {
    set complexNumbers[idx] = ComplexPolar(amplitudes[idx], phases[idx]);
}
let op = StatePreparationComplexCoefficients(complexNumbers);
using (qubits = Qubit[2]) {
    let qubitsLE = LittleEndian(qubits);
    op(qubitsLE);
}
```

## <a name="remarks"></a><span data-ttu-id="23493-119">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="23493-119">Remarks</span></span>

<span data-ttu-id="23493-120">A negatív bemeneti együtthatók $r _j < $0-as értéke pozitív a $ | r_j | $ értékkel.</span><span class="sxs-lookup"><span data-stu-id="23493-120">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="23493-121">`coefficients` a (r_j, t_j) = (0,0, 0,0) $ értékkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.</span><span class="sxs-lookup"><span data-stu-id="23493-121">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>