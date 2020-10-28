---
uid: Microsoft.Quantum.Preparation.StatePreparationPositiveCoefficients
title: StatePreparationPositiveCoefficients függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: StatePreparationPositiveCoefficients
qsharp.summary: >-
  Returns an operation that prepares the given quantum state.

  The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.

  The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}. \end{align} $$
ms.openlocfilehash: 39d961c71d231e7b51290f81c20c8c6b48c7e0b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722898"
---
# <a name="statepreparationpositivecoefficients-function"></a><span data-ttu-id="4d09d-102">StatePreparationPositiveCoefficients függvény</span><span class="sxs-lookup"><span data-stu-id="4d09d-102">StatePreparationPositiveCoefficients function</span></span>

<span data-ttu-id="4d09d-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="4d09d-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="4d09d-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4d09d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4d09d-105">Egy olyan műveletet ad vissza, amely előkészíti a megadott kvantum-állapotot.</span><span class="sxs-lookup"><span data-stu-id="4d09d-105">Returns an operation that prepares the given quantum state.</span></span>

<span data-ttu-id="4d09d-106">A visszaadott művelet $U $ előkészít egy tetszőleges kvantum-állapotot ($ \ket{\psi} $) a következő pozitív együtthatókkal: $ \ alpha_j \ge $0 az $n $-qubit számítási alapja $ \ket{0...0} $.</span><span class="sxs-lookup"><span data-stu-id="4d09d-106">The returned operation $U$ prepares an arbitrary quantum state $\ket{\psi}$ with positive coefficients $\alpha_j\ge 0$ from the $n$-qubit computational basis state $\ket{0...0}$.</span></span>

<span data-ttu-id="4d09d-107">Az U művelet az újonnan lefoglalt regisztrációhoz $ $ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\ sum_ {j = 0} ^ {2 ^ n-1} \ alpha_j \ket{j}}{\sqrt{\ sum_ {j = 0} ^ {2 ^ n-1} | \ alpha_j | ^ 2}}.</span><span class="sxs-lookup"><span data-stu-id="4d09d-107">The action of U on a newly-allocated register is given by $$ \begin{align} U \ket{0\cdots 0} = \ket{\psi} = \frac{\sum_{j=0}^{2^n-1}\alpha_j \ket{j}}{\sqrt{\sum_{j=0}^{2^n-1}|\alpha_j|^2}}.</span></span>
<span data-ttu-id="4d09d-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="4d09d-108">\end{align} $$</span></span>

```qsharp
function StatePreparationPositiveCoefficients (coefficients : Double[]) : (Microsoft.Quantum.Arithmetic.LittleEndian => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="4d09d-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4d09d-109">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="4d09d-110">együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4d09d-110">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4d09d-111">Legfeljebb $2 ^ n $ együttható, $ \ alpha_j $.</span><span class="sxs-lookup"><span data-stu-id="4d09d-111">Array of up to $2^n$ coefficients $\alpha_j$.</span></span> <span data-ttu-id="4d09d-112">A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.</span><span class="sxs-lookup"><span data-stu-id="4d09d-112">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>



## <a name="output--littleendian--unit-adj--ctl"></a><span data-ttu-id="4d09d-113">Kimenet: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [egység](xref:microsoft.quantum.lang-ref.unit) , adj + CTL</span><span class="sxs-lookup"><span data-stu-id="4d09d-113">Output : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="4d09d-114">Az állapot-előkészítési egységes művelet $U $.</span><span class="sxs-lookup"><span data-stu-id="4d09d-114">A state-preparation unitary operation $U$.</span></span>

## <a name="remarks"></a><span data-ttu-id="4d09d-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="4d09d-115">Remarks</span></span>

<span data-ttu-id="4d09d-116">A negatív bemeneti együtthatók $ \ alpha_j < $0 a (z) $ | \ alpha_j | $ értékű pozitív értékkel lesznek kezelve.</span><span class="sxs-lookup"><span data-stu-id="4d09d-116">Negative input coefficients $\alpha_j < 0$ will be treated as though positive with value $|\alpha_j|$.</span></span> <span data-ttu-id="4d09d-117">`coefficients` a $ \ alpha_j = $0,0 elemekkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.</span><span class="sxs-lookup"><span data-stu-id="4d09d-117">`coefficients` will be padded with elements $\alpha_j = 0.0$ if fewer than $2^n$ are specified.</span></span>