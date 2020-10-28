---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 407a139da816281346eb06849f81e91b83202653
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712969"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="e751a-102">AssertOperationsEqualInPlace művelet</span><span class="sxs-lookup"><span data-stu-id="e751a-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="e751a-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e751a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e751a-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e751a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e751a-105">A két művelet miatt a azt állítja, hogy az összes bemeneti állapot esetében azonos módon működnek.</span><span class="sxs-lookup"><span data-stu-id="e751a-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="e751a-106">Ez az állítás a műveleteknek a (z) $V _0 \otimes... \otimes V_ {n-1} $, ahol a $V _k $ egyike a (z) $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ és $ \ket{i} $ (+ 1 Eigenstate Pauli Y operátor) állapotának ellenőrzésével valósul meg.</span><span class="sxs-lookup"><span data-stu-id="e751a-106">This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).</span></span>

<span data-ttu-id="e751a-107">Ez az állítás $n $ qubits használ, és több hívást igényel a műveletekhez képest.</span><span class="sxs-lookup"><span data-stu-id="e751a-107">This assertion uses $n$ qubits and requires multiple calls of the operations being compared.</span></span>

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="e751a-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e751a-108">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="e751a-109">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e751a-109">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e751a-110">Azon qubits száma, $n $, amelyeken a műveletek `givenU` és `expectedU` működnek.</span><span class="sxs-lookup"><span data-stu-id="e751a-110">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="e751a-111">givenU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e751a-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="e751a-112">$N $ qubits műveletet kell ellenőrizni.</span><span class="sxs-lookup"><span data-stu-id="e751a-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit-adj"></a><span data-ttu-id="e751a-113">expectedU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="e751a-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="e751a-114">A (z) $n $ qubits hivatkozási művelete, amelyet `givenU` össze kell hasonlítani.</span><span class="sxs-lookup"><span data-stu-id="e751a-114">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e751a-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e751a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="e751a-116">Referencia</span><span class="sxs-lookup"><span data-stu-id="e751a-116">References</span></span>

<span data-ttu-id="e751a-117">A $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ és $ \ket{i} $ állapotú államok alapja Chuang-Nielsen a következő: [ *i. L., M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).</span><span class="sxs-lookup"><span data-stu-id="e751a-117">The basis of states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ is the Chuang-Nielsen basis, described in [ *I. L. Chuang, M. A. Nielsen* ](https://arxiv.org/abs/quant-ph/9610001).</span></span>

## <a name="see-also"></a><span data-ttu-id="e751a-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e751a-118">See Also</span></span>

- [<span data-ttu-id="e751a-119">Microsoft. Quantum. Diagnostics. AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="e751a-119">Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)