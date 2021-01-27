---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 7c330ebdc156e60713a734d39a3600ee1326563c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853488"
---
# <a name="assertoperationsequalinplace-operation"></a><span data-ttu-id="20437-102">AssertOperationsEqualInPlace művelet</span><span class="sxs-lookup"><span data-stu-id="20437-102">AssertOperationsEqualInPlace operation</span></span>

<span data-ttu-id="20437-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="20437-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="20437-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="20437-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="20437-105">A két művelet miatt a azt állítja, hogy az összes bemeneti állapot esetében azonos módon működnek.</span><span class="sxs-lookup"><span data-stu-id="20437-105">Given two operations, asserts that they act identically for all input states.</span></span>

<span data-ttu-id="20437-106">Ez az állítás a műveleteknek a (z) $V _0 \otimes... \otimes V_ {n-1} $, ahol a $V _k $ egyike a (z) $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ és $ \ket{i} $ (+ 1 Eigenstate Pauli Y operátor) állapotának ellenőrzésével valósul meg.</span><span class="sxs-lookup"><span data-stu-id="20437-106">This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).</span></span>

<span data-ttu-id="20437-107">Ez az állítás $n $ qubits használ, és több hívást igényel a műveletekhez képest.</span><span class="sxs-lookup"><span data-stu-id="20437-107">This assertion uses $n$ qubits and requires multiple calls of the operations being compared.</span></span>

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a><span data-ttu-id="20437-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="20437-108">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="20437-109">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="20437-109">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="20437-110">Azon qubits száma, $n $, amelyeken a műveletek `givenU` és `expectedU` működnek.</span><span class="sxs-lookup"><span data-stu-id="20437-110">The number of qubits $n$ that the operations `givenU` and `expectedU` operate on.</span></span>


### <a name="givenu--qubit--unit"></a><span data-ttu-id="20437-111">givenU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20437-111">givenU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="20437-112">$N $ qubits műveletet kell ellenőrizni.</span><span class="sxs-lookup"><span data-stu-id="20437-112">Operation on $n$ qubits to be checked.</span></span>


### <a name="expectedu--qubit--unit--is-adj"></a><span data-ttu-id="20437-113">expectedU: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20437-113">expectedU : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="20437-114">A (z) $n $ qubits hivatkozási művelete, amelyet `givenU` össze kell hasonlítani.</span><span class="sxs-lookup"><span data-stu-id="20437-114">Reference operation on $n$ qubits that `givenU` is to be compared against.</span></span>



## <a name="output--unit"></a><span data-ttu-id="20437-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="20437-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="20437-116">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="20437-116">References</span></span>

<span data-ttu-id="20437-117">A $ \ket {0} $, $ \ket {1} $, $ \ket{+} $ és $ \ket{i} $ állapotú államok alapja Chuang-Nielsen a következő: [ *i. L., M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001).</span><span class="sxs-lookup"><span data-stu-id="20437-117">The basis of states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ is the Chuang-Nielsen basis, described in [ *I. L. Chuang, M. A. Nielsen* ](https://arxiv.org/abs/quant-ph/9610001).</span></span>

## <a name="see-also"></a><span data-ttu-id="20437-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="20437-118">See Also</span></span>

- [<span data-ttu-id="20437-119">Microsoft. Quantum. Diagnostics. AssertOperationsEqualReferenced</span><span class="sxs-lookup"><span data-stu-id="20437-119">Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)