---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: ApplyCNOTChainWithTarget művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: fd0a0f3e1db89946aec2c63f3cde7a021608eea5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718361"
---
# <a name="applycnotchainwithtarget-operation"></a><span data-ttu-id="62894-102">ApplyCNOTChainWithTarget művelet</span><span class="sxs-lookup"><span data-stu-id="62894-102">ApplyCNOTChainWithTarget operation</span></span>

<span data-ttu-id="62894-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="62894-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="62894-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="62894-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="62894-105">Kiszámítja egy qubits-tömb paritását egy célként megadott qubit.</span><span class="sxs-lookup"><span data-stu-id="62894-105">Computes the parity of an array of qubits into a target qubit.</span></span>

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="62894-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="62894-106">Description</span></span>

<span data-ttu-id="62894-107">Ha a tömb kezdetben a $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\text{Target}}} $, a végleges állapotot a $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\text{Target}}} $.</span><span class="sxs-lookup"><span data-stu-id="62894-107">If the array is initially in the state $\ket{q_0} \ket{q_1} \cdots \ket{q_{\text{target}}}$, the final state is given by $\ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_{n - 1} \oplus \cdots \oplus q_0 \oplus q_{\text{target}}}$.</span></span>

## <a name="input"></a><span data-ttu-id="62894-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="62894-108">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="62894-109">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="62894-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="62894-110">Azon qubits tömbje, amelyeken a paritás kiszámítása történik.</span><span class="sxs-lookup"><span data-stu-id="62894-110">Array of qubits on which the parity is computed.</span></span>


### <a name="targetqubit--qubit"></a><span data-ttu-id="62894-111">targetQubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="62894-111">targetQubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="62894-112">A végső qubit, amelybe a "qubits" paritása XORed.</span><span class="sxs-lookup"><span data-stu-id="62894-112">Final qubit into which the parity of 'qubits' is XORed.</span></span>



## <a name="output--unit"></a><span data-ttu-id="62894-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62894-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="62894-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="62894-114">Remarks</span></span>

<span data-ttu-id="62894-115">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="62894-115">The following are equivalent:</span></span>

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

<span data-ttu-id="62894-116">és</span><span class="sxs-lookup"><span data-stu-id="62894-116">and</span></span>

```qsharp
ApplyCNOTChain(qs);
```