---
uid: Microsoft.Quantum.Canon.ApplyDiagonalUnitary
title: ApplyDiagonalUnitary művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits.
ms.openlocfilehash: 6ecacf6e4fe2c505036de208c8aeb5350e479e3c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718288"
---
# <a name="applydiagonalunitary-operation"></a><span data-ttu-id="6d840-102">ApplyDiagonalUnitary művelet</span><span class="sxs-lookup"><span data-stu-id="6d840-102">ApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="6d840-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6d840-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6d840-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6d840-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6d840-105">Összetett fázisokat alkalmaz a qubits regiszterének numerikus állapotára.</span><span class="sxs-lookup"><span data-stu-id="6d840-105">Applies an array of complex phases to numeric basis states of a register of qubits.</span></span>

```qsharp
operation ApplyDiagonalUnitary (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="6d840-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="6d840-106">Description</span></span>

<span data-ttu-id="6d840-107">Ez a művelet egy olyan átlós egységes implementációt valósít meg, amely egy összetett fázist alkalmaz $e ^ {i \ theta_j} $ értékre a következő $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="6d840-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="6d840-108">Ez a művelet különösen a következő lehet:</span><span class="sxs-lookup"><span data-stu-id="6d840-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="6d840-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="6d840-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="6d840-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="6d840-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="6d840-111">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6d840-111">Input</span></span>

### <a name="coefficients--double"></a><span data-ttu-id="6d840-112">együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="6d840-112">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="6d840-113">Legfeljebb $2 ^ n $ együttható, $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="6d840-113">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="6d840-114">A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.</span><span class="sxs-lookup"><span data-stu-id="6d840-114">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="6d840-115">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="6d840-115">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="6d840-116">$n $-qubit-vezérlő regisztrálása, amely kis endian formátumban kódolja a szám állapotot $ \ket{j} $ értékre.</span><span class="sxs-lookup"><span data-stu-id="6d840-116">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6d840-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6d840-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="6d840-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6d840-118">Remarks</span></span>

<span data-ttu-id="6d840-119">`coefficients` a $ \ theta_j = $0,0 elemekkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.</span><span class="sxs-lookup"><span data-stu-id="6d840-119">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="6d840-120">Referencia</span><span class="sxs-lookup"><span data-stu-id="6d840-120">References</span></span>

- <span data-ttu-id="6d840-121">A kvantum-logikai áramkörök összeszintézise: Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="6d840-121">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="6d840-122">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="6d840-122">See Also</span></span>

- [<span data-ttu-id="6d840-123">Microsoft. Quantum. Canon. ApproximatelyApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="6d840-123">Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary)