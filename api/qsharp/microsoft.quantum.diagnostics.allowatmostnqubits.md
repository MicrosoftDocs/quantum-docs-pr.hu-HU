---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: 3aa80767ac0f752e7be0efa2966c580ca3cb8f19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830914"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="c3a12-102">AllowAtMostNQubits művelet</span><span class="sxs-lookup"><span data-stu-id="c3a12-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="c3a12-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="c3a12-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="c3a12-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c3a12-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c3a12-105">A művelet és a adjoint meghívása között a azt állítja, hogy a további qubits száma a using utasítások használatával történik.</span><span class="sxs-lookup"><span data-stu-id="c3a12-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="c3a12-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c3a12-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="c3a12-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c3a12-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c3a12-108">A lefoglalható qubits maximális száma.</span><span class="sxs-lookup"><span data-stu-id="c3a12-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="c3a12-109">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="c3a12-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="c3a12-110">Hiba esetén megjelenítendő üzenet.</span><span class="sxs-lookup"><span data-stu-id="c3a12-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c3a12-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c3a12-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="c3a12-112">Példa</span><span class="sxs-lookup"><span data-stu-id="c3a12-112">Example</span></span>

<span data-ttu-id="c3a12-113">A következő kódrészlet meghiúsul, amikor a rendszer végrehajtja a diagnosztikai szolgáltatást támogató gépeken:</span><span class="sxs-lookup"><span data-stu-id="c3a12-113">The following snippet will fail when executed on machines which support this diagnostic:</span></span>

```qsharp
within {
    AllowAtMostNQubits(3, "Too many qubits allocated.");
} apply {
    // Fails since this allocates four qubits.
    using (register = Qubit[4]) {
    }
}
```

## <a name="remarks"></a><span data-ttu-id="c3a12-114">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c3a12-114">Remarks</span></span>

<span data-ttu-id="c3a12-115">Lehetséges, hogy ezt a műveletet egy nem op-vel rendelkező célok helyettesítik, amelyek nem támogatják azt.</span><span class="sxs-lookup"><span data-stu-id="c3a12-115">This operation may be replaced by a no-op on targets which do not support it.</span></span>