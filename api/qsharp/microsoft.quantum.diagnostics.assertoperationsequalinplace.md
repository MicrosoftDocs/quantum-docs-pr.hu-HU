---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 9b17bac9d95baf5a542604892c64130bf35d7f69
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202430"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="0e625-102">AssertOperationsEqualInPlace művelet</span><span class="sxs-lookup"><span data-stu-id="0e625-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="0e625-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="0e625-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="0e625-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0e625-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0e625-105">A két művelet miatt a azt állítja, hogy az összes bemeneti állapot esetében azonos módon működnek.</span><span class="sxs-lookup"><span data-stu-id="0e625-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="0e625-106">Ez az állítás a műveleteknek a (z) $V _0 \otimes... \otimes V_ {n-1} $, ahol a $V _k $ egyike a (z) $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ és $ \ket{i} $ (+ 1 Eigenstate Pauli Y operátor) állapotának ellenőrzésével valósul meg.</span><span class="sxs-lookup"><span data-stu-id="0e625-106">This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).</span></span>

<span data-ttu-id="0e625-107">Ez az állítás $n $ qubits használ, és több hívást igényel a műveletekhez képest.</span><span class="sxs-lookup"><span data-stu-id="0e625-107">This assertion uses $n$ qubits and requires multiple calls of the operations being compared.</span></span>

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="0e625-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0e625-108">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="0e625-109">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0e625-109">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0e625-110">Azon qubits száma, $n $, amelyeken a műveletek `givenU` és `expectedU` működnek.</span><span class="sxs-lookup"><span data-stu-id="0e625-110">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="0e625-111">givenU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e625-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="0e625-112">$N $ qubits műveletet kell ellenőrizni.</span><span class="sxs-lookup"><span data-stu-id="0e625-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="0e625-113">expectedU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e625-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="0e625-114">A (z) $n $ qubits hivatkozási művelete, amelyet `givenU` össze kell hasonlítani.</span><span class="sxs-lookup"><span data-stu-id="0e625-114">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0e625-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0e625-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="0e625-116">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="0e625-116">References</span></span>

<span data-ttu-id="0e625-117">A $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ és $ \ket{i} $ állapotú államok alapja Chuang-Nielsen a következő: [ *i. L., M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).</span><span class="sxs-lookup"><span data-stu-id="0e625-117">The basis of states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ is the Chuang-Nielsen basis, described in [ *I. L. Chuang, M. A. Nielsen* ](https://arxiv.org/abs/quant-ph/9610001).</span></span>

## <a name="see-also"></a><span data-ttu-id="0e625-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="0e625-118">See Also</span></span>

- [<span data-ttu-id="0e625-119">Microsoft. Quantum. Diagnostics. AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="0e625-119">Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)