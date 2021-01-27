---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: 85ff04bbad9dc2ed0f803db65508fdfbb0d22c56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843411"
---
# <a name="assertprobint-operation"></a><span data-ttu-id="628ec-102">AssertProbInt művelet</span><span class="sxs-lookup"><span data-stu-id="628ec-102">AssertProbInt operation</span></span>

<span data-ttu-id="628ec-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="628ec-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="628ec-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="628ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="628ec-105">Azt állítja, hogy a kvantum-regiszter adott állapotának valószínűsége a várt érték.</span><span class="sxs-lookup"><span data-stu-id="628ec-105">Asserts that the probability of a specific state of a quantum register has the expected value.</span></span>

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a><span data-ttu-id="628ec-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="628ec-106">Description</span></span>

<span data-ttu-id="628ec-107">Adott egy $n $-qubit Quantum State $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $, azt állítja, hogy a $ | \ alpha_j | ^ 2 $ a (z) $j $ indexelt állapotú $ \ket{j} $ indexben a várt érték szerepel.</span><span class="sxs-lookup"><span data-stu-id="628ec-107">Given an $n$-qubit quantum state $\ket{\psi}=\sum^{2^n-1}_{j=0}\alpha_j \ket{j}$, asserts that the probability $|\alpha_j|^2$ of the state $\ket{j}$ indexed by $j$ has the expected value.</span></span>

## <a name="input"></a><span data-ttu-id="628ec-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="628ec-108">Input</span></span>

### <a name="stateindex--int"></a><span data-ttu-id="628ec-109">stateIndex: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="628ec-109">stateIndex : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="628ec-110">Egy regiszter által jelzett, $ \ket{j} $ állapotú $ $j $ index `LittleEndian` .</span><span class="sxs-lookup"><span data-stu-id="628ec-110">The index $j$ of the state $\ket{j}$ represented by a `LittleEndian` register.</span></span>


### <a name="expected--double"></a><span data-ttu-id="628ec-111">várt érték: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="628ec-111">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="628ec-112">A várt érték: $ | \ alpha_j | ^ 2 $.</span><span class="sxs-lookup"><span data-stu-id="628ec-112">The expected value of $|\alpha_j|^2$.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="628ec-113">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="628ec-113">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="628ec-114">A qubit regisztrálja a $ \ket{\psi} $ tárolót kis endian formátumban.</span><span class="sxs-lookup"><span data-stu-id="628ec-114">The qubit register that stores $\ket{\psi}$ in little-endian format.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="628ec-115">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="628ec-115">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="628ec-116">A tényleges és a várt érték közötti különbség abszolút tűréshatára.</span><span class="sxs-lookup"><span data-stu-id="628ec-116">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="628ec-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="628ec-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="628ec-118">Példa</span><span class="sxs-lookup"><span data-stu-id="628ec-118">Example</span></span>

<span data-ttu-id="628ec-119">Tegyük fel, hogy a `qubits` regisztráció egy 3 qubit Quantum State $ \ket{\psi} = \ SQRT {1/8} \ ket {0} + \ SQRT {7/8} \ ket {6} $ értékű, kis endian formátumban kódolja.</span><span class="sxs-lookup"><span data-stu-id="628ec-119">Suppose that the `qubits` register encodes a 3-qubit quantum state $\ket{\psi}=\sqrt{1/8}\ket{0}+\sqrt{7/8}\ket{6}$ in little-endian format.</span></span>
<span data-ttu-id="628ec-120">Ez azt jelenti, hogy a szám állapota $ \ket {0} \equiv\ket {0} \ket {0} \ket {0} $ és $ \ket {6} \equiv\ket {0} \ket {1} \ket {1} $.</span><span class="sxs-lookup"><span data-stu-id="628ec-120">This means that the number states $\ket{0}\equiv\ket{0}\ket{0}\ket{0}$ and $\ket{6}\equiv\ket{0}\ket{1}\ket{1}$.</span></span> <span data-ttu-id="628ec-121">Ezután a következő érvényesítések sikeresek lesznek:</span><span class="sxs-lookup"><span data-stu-id="628ec-121">Then the following asserts succeed:</span></span>

```qsharp
AssertProbInt(0, 0.125, qubits, 10e-10);
AssertProbInt(6, 0.875, qubits, 10e-10);
```