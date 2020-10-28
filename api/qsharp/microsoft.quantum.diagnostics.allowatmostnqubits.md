---
uid: Microsoft.Quantum.Diagnostics.AllowAtMostNQubits
title: AllowAtMostNQubits művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllowAtMostNQubits
qsharp.summary: Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.
ms.openlocfilehash: ddbed96df0d95cfd78730c091a6a81ee6e49c349
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713053"
---
# <a name="allowatmostnqubits-operation"></a><span data-ttu-id="691c3-102">AllowAtMostNQubits művelet</span><span class="sxs-lookup"><span data-stu-id="691c3-102">AllowAtMostNQubits operation</span></span>

<span data-ttu-id="691c3-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="691c3-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="691c3-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="691c3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="691c3-105">A művelet és a adjoint meghívása között a azt állítja, hogy a további qubits száma a using utasítások használatával történik.</span><span class="sxs-lookup"><span data-stu-id="691c3-105">Between a call to this operation and its adjoint, asserts that at most a given number of additional qubits are allocated with using statements.</span></span>

```qsharp
operation AllowAtMostNQubits (nQubits : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="691c3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="691c3-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="691c3-107">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="691c3-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="691c3-108">A lefoglalható qubits maximális száma.</span><span class="sxs-lookup"><span data-stu-id="691c3-108">The maximum number of qubits that may be allocated.</span></span>


### <a name="message--string"></a><span data-ttu-id="691c3-109">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="691c3-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="691c3-110">Hiba esetén megjelenítendő üzenet.</span><span class="sxs-lookup"><span data-stu-id="691c3-110">A message to be displayed upon failure.</span></span>



## <a name="output--unit"></a><span data-ttu-id="691c3-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="691c3-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="691c3-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="691c3-112">Remarks</span></span>

<span data-ttu-id="691c3-113">Lehetséges, hogy ezt a műveletet egy nem op-vel rendelkező célok helyettesítik, amelyek nem támogatják azt.</span><span class="sxs-lookup"><span data-stu-id="691c3-113">This operation may be replaced by a no-op on targets which do not support it.</span></span>