---
uid: Microsoft.Quantum.Preparation.StatePreparationComplexCoefficients
title: StatePreparationComplexCoefficients függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationComplexCoefficients
qsharp.summary: >-
  Returns an operation that prepares a specific quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}. \end{align} $$
ms.openlocfilehash: 02e3d2fcf21b5bb4ed1bf7aa931597f918a1d369
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722912"
---
# <a name="statepreparationcomplexcoefficients-function"></a><span data-ttu-id="d9bb2-102">StatePreparationComplexCoefficients függvény</span><span class="sxs-lookup"><span data-stu-id="d9bb2-102">StatePreparationComplexCoefficients function</span></span>

<span data-ttu-id="d9bb2-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="d9bb2-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="d9bb2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d9bb2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d9bb2-105">Egy olyan műveletet ad vissza, amely egy adott kvantum-állapotot készít elő.</span><span class="sxs-lookup"><span data-stu-id="d9bb2-105">Returns an operation that prepares a specific quantum state.</span></span>

<span data-ttu-id="d9bb2-106">A visszaadott művelet $U $ felkészít egy tetszőleges kvantum-állapotot ($ \ket{\psi} $) összetett együtthatókkal $r _j e ^ {i t_j} $ értéket a $n $ qubit számítási alapból $ \ket{0...0} $ értékre.</span><span class="sxs-lookup"><span data-stu-id="d9bb2-106">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with complex coefficients $r_j e^{i t_j}$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="d9bb2-107">Az U egy újonnan lefoglalt regisztrációra vonatkozó műveletét $ $ \begin{align} U\ket {0... 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} r_j e ^ {i t_j} \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | r_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="d9bb2-107">The action of U on a newly-allocated register is given by $$ \begin{align} U\ket{0...0}=\ket{\psi}=\frac{\sum_{j=0}^{2^n-1}r_j e^{i t_j}\ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|r_j|^2}}.</span></span>
<span data-ttu-id="d9bb2-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="d9bb2-108">\end{align} $$</span></span>

```qsharp
function StatePreparationComplexCoefficients (coefficients : Microsoft.Quantum.Math.ComplexPolar[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="d9bb2-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d9bb2-109">Input</span></span>

### <a name="coefficients--complexpolar"></a><span data-ttu-id="d9bb2-110">együtthatók: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span><span class="sxs-lookup"><span data-stu-id="d9bb2-110">coefficients : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)[]</span></span>

<span data-ttu-id="d9bb2-111">Legfeljebb $2 ^ n $ összetett együtthatók, amelyek abszolút értéke és a $ (r_j, t_j) $.</span><span class="sxs-lookup"><span data-stu-id="d9bb2-111">Array of up to $2^n$ complex coefficients represented by their absolute value and phase $(r_j, t_j)$.</span></span> <span data-ttu-id="d9bb2-112">A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.</span><span class="sxs-lookup"><span data-stu-id="d9bb2-112">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="d9bb2-113">Kimenet: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) , adj + CTL</span><span class="sxs-lookup"><span data-stu-id="d9bb2-113">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="d9bb2-114">Az állapot-előkészítési egységes művelet $U $.</span><span class="sxs-lookup"><span data-stu-id="d9bb2-114">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="d9bb2-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d9bb2-115">Remarks</span></span>

<span data-ttu-id="d9bb2-116">A negatív bemeneti együtthatók $r _j < $0-as értéke pozitív a $ | r_j | $ értékkel.</span><span class="sxs-lookup"><span data-stu-id="d9bb2-116">Negative input coefficients $r_j < 0$ will be treated as though positive with value $|r_j|$.</span></span> <span data-ttu-id="d9bb2-117">`coefficients` a (r_j, t_j) = (0,0, 0,0) $ értékkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.</span><span class="sxs-lookup"><span data-stu-id="d9bb2-117">`coefficients` will be padded with elements $(r_j, t_j) = (0.0, 0.0)$ if fewer than $2^n$ are specified.</span></span>