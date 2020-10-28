---
uid: Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary
title: ApproximatelyApplyDiagonalUnitary művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 9d9b1ced320b142aef2a2cd8f3335f855d37048f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716819"
---
# <a name="approximatelyapplydiagonalunitary-operation"></a><span data-ttu-id="366dc-102">ApproximatelyApplyDiagonalUnitary művelet</span><span class="sxs-lookup"><span data-stu-id="366dc-102">ApproximatelyApplyDiagonalUnitary operation</span></span>

<span data-ttu-id="366dc-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="366dc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="366dc-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="366dc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="366dc-105">Összetett fázisokat alkalmaz a qubits regiszterének numerikus állapotára, és lerövidíti a kis forgási szögeket egy adott tolerancia alapján.</span><span class="sxs-lookup"><span data-stu-id="366dc-105">Applies an array of complex phases to numeric basis states of a register of qubits, truncating small rotation angles according to a given tolerance.</span></span>

```qsharp
operation ApproximatelyApplyDiagonalUnitary (tolerance : Double, coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="366dc-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="366dc-106">Description</span></span>

<span data-ttu-id="366dc-107">Ez a művelet egy olyan átlós egységes implementációt valósít meg, amely egy összetett fázist alkalmaz $e ^ {i \ theta_j} $ értékre a következő $n $-qubit Number State $ \ket{j} $.</span><span class="sxs-lookup"><span data-stu-id="366dc-107">This operation implements a diagonal unitary that applies a complex phase $e^{i \theta_j}$ on the $n$-qubit number state $\ket{j}$.</span></span>
<span data-ttu-id="366dc-108">Ez a művelet különösen a következő lehet:</span><span class="sxs-lookup"><span data-stu-id="366dc-108">In particular, this operation can be represented by the unitary</span></span>

<span data-ttu-id="366dc-109">$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}.</span><span class="sxs-lookup"><span data-stu-id="366dc-109">$$ \begin{align} U = \sum^{2^n-1}_{j=0}e^{i\theta_j}\ket{j}\bra{j}.</span></span>
<span data-ttu-id="366dc-110">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="366dc-110">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="366dc-111">Bevitel</span><span class="sxs-lookup"><span data-stu-id="366dc-111">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="366dc-112">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="366dc-112">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="366dc-113">Az a tűréshatár, amely alatt a kis együtthatók csonkítva vannak.</span><span class="sxs-lookup"><span data-stu-id="366dc-113">A tolerance below which small coefficients are truncated.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="366dc-114">együtthatók: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="366dc-114">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="366dc-115">Legfeljebb $2 ^ n $ együttható, $ \ theta_j $.</span><span class="sxs-lookup"><span data-stu-id="366dc-115">Array of up to $2^n$ coefficients $\theta_j$.</span></span> <span data-ttu-id="366dc-116">A $j $ th együttható a $ \ket{j} $ kódolású számú állapotot indexeli a kis endian formátumban.</span><span class="sxs-lookup"><span data-stu-id="366dc-116">The $j$th coefficient indexes the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="366dc-117">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="366dc-117">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="366dc-118">$n $-qubit-vezérlő regisztrálása, amely kis endian formátumban kódolja a szám állapotot $ \ket{j} $ értékre.</span><span class="sxs-lookup"><span data-stu-id="366dc-118">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>



## <a name="output--unit"></a><span data-ttu-id="366dc-119">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="366dc-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="366dc-120">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="366dc-120">Remarks</span></span>

<span data-ttu-id="366dc-121">`coefficients` a $ \ theta_j = $0,0 elemekkel lesz feltöltve, ha kevesebb, mint $2 ^ n $ van megadva.</span><span class="sxs-lookup"><span data-stu-id="366dc-121">`coefficients` will be padded with elements $\theta_j = 0.0$ if fewer than $2^n$ are specified.</span></span>

## <a name="references"></a><span data-ttu-id="366dc-122">Referencia</span><span class="sxs-lookup"><span data-stu-id="366dc-122">References</span></span>

- <span data-ttu-id="366dc-123">A kvantum-logikai áramkörök összeszintézise: Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span><span class="sxs-lookup"><span data-stu-id="366dc-123">Synthesis of Quantum Logic Circuits Vivek V. Shende, Stephen S. Bullock, Igor L. Markov https://arxiv.org/abs/quant-ph/0406176</span></span>

## <a name="see-also"></a><span data-ttu-id="366dc-124">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="366dc-124">See Also</span></span>

- [<span data-ttu-id="366dc-125">Microsoft. Quantum. Canon. ApplyDiagonalUnitary</span><span class="sxs-lookup"><span data-stu-id="366dc-125">Microsoft.Quantum.Canon.ApplyDiagonalUnitary</span></span>](xref:Microsoft.Quantum.Canon.ApplyDiagonalUnitary)