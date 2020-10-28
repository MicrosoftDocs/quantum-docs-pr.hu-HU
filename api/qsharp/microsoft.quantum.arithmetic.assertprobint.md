---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: a8e4217e18528adc0aa9923f1c0dcfb59e1d2488
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721361"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="3b88a-102">AssertProbInt művelet</span><span class="sxs-lookup"><span data-stu-id="3b88a-102">AssertProbInt operation</span></span>

<span data-ttu-id="3b88a-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="3b88a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="3b88a-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b88a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b88a-105">Azt állítja, hogy a kvantum-regiszter adott állapotának valószínűsége a várt érték.</span><span class="sxs-lookup"><span data-stu-id="3b88a-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="3b88a-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="3b88a-106">Description</span></span>

<span data-ttu-id="3b88a-107">Adott egy $n $-qubit Quantum State $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, azt állítja, hogy a $ | \ alpha_j | ^ 2 $ a (z) $j $ indexelt állapotú $ \ket{j} $ indexben a várt érték szerepel.</span><span class="sxs-lookup"><span data-stu-id="3b88a-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="3b88a-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3b88a-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="3b88a-109">stateIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3b88a-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3b88a-110">Egy regiszter által jelzett, $ \ket{j} $ állapotú $ $j $ index `LittleEndian` .</span><span class="sxs-lookup"><span data-stu-id="3b88a-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="3b88a-111">várt érték: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3b88a-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3b88a-112">A várt érték: $ | \ alpha_j | ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="3b88a-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="3b88a-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="3b88a-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="3b88a-114">A qubit regisztrálja a $ \ket{\psi} $ tárolót kis endian formátumban.</span><span class="sxs-lookup"><span data-stu-id="3b88a-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="3b88a-115">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3b88a-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3b88a-116">A tényleges és a várt érték közötti különbség abszolút tűréshatára.</span><span class="sxs-lookup"><span data-stu-id="3b88a-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3b88a-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3b88a-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

