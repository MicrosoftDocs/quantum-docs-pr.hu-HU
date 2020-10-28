---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: ExpFrac művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: d11912a272387b087098f59e7ac071534b01c054
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711485"
---
# <a name="expfrac-operation"></a><span data-ttu-id="46eeb-102">ExpFrac művelet</span><span class="sxs-lookup"><span data-stu-id="46eeb-102">ExpFrac operation</span></span>

<span data-ttu-id="46eeb-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="46eeb-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="46eeb-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="46eeb-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="46eeb-105">Egy több qubit Pauli operátor exponenciális értékének alkalmazása egy dyadic-frakció által megadott argumentummal.</span><span class="sxs-lookup"><span data-stu-id="46eeb-105">Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.</span></span>

<span data-ttu-id="46eeb-106">\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}, \end{align}, ahol $P _i $ a $i $ th eleme `paulis` , és hol $N = $ `Length(paulis)` .</span><span class="sxs-lookup"><span data-stu-id="46eeb-106">\begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.</span></span>

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="46eeb-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="46eeb-107">Input</span></span>

### <a name="paulis--pauli"></a><span data-ttu-id="46eeb-108">Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="46eeb-108">paulis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="46eeb-109">A qubit Pauli-értékek tömbje, amely az egyes qubit a kétféle termékre vonatkozó tényezőket jelzi.</span><span class="sxs-lookup"><span data-stu-id="46eeb-109">Array of single-qubit Pauli values indicating the tensor product factors on each qubit.</span></span>


### <a name="numerator--int"></a><span data-ttu-id="46eeb-110">számláló: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="46eeb-110">numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="46eeb-111">A számláló ($k $) annak a szögnek a dyadic-frakciós ábrázolásában, amellyel a qubit-regisztrációt el kell forgatni.</span><span class="sxs-lookup"><span data-stu-id="46eeb-111">Numerator ($k$) in the dyadic fraction representation of the angle by which the qubit register is to be rotated.</span></span>


### <a name="power--int"></a><span data-ttu-id="46eeb-112">teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="46eeb-112">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="46eeb-113">A két ($n $) ereje annak a szögnek a nevezőjét határozza meg, amellyel a qubit-regisztráció el lesz forgatva.</span><span class="sxs-lookup"><span data-stu-id="46eeb-113">Power of two ($n$) specifying the denominator of the angle by which the qubit register is to be rotated.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="46eeb-114">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="46eeb-114">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="46eeb-115">Regisztrálja, hogy a megadott rotációt alkalmazza a következőre:.</span><span class="sxs-lookup"><span data-stu-id="46eeb-115">Register to apply the given rotation to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="46eeb-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="46eeb-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

