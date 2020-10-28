---
uid: Microsoft.Quantum.Canon.PermuteQubits
title: PermuteQubits művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: PermuteQubits
qsharp.summary: Permutes qubits by using the SWAP operation.
ms.openlocfilehash: 0f4d8819d5b08f4d5370f8fdc407b2eb2a3e5f21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715657"
---
# <a name="permutequbits-operation"></a><span data-ttu-id="0aea9-102">PermuteQubits művelet</span><span class="sxs-lookup"><span data-stu-id="0aea9-102">PermuteQubits operation</span></span>

<span data-ttu-id="0aea9-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0aea9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0aea9-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0aea9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0aea9-105">A Permutes qubits a SWAP művelettel.</span><span class="sxs-lookup"><span data-stu-id="0aea9-105">Permutes qubits by using the SWAP operation.</span></span>

```qsharp
operation PermuteQubits (ordering : Int[], register : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="0aea9-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0aea9-106">Input</span></span>

### <a name="ordering--int"></a><span data-ttu-id="0aea9-107">megrendelés: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0aea9-107">ordering : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0aea9-108">Ismerteti a qubits új sorrendjét, ahol a qubit az indexben most az [i] sorrendbe kerül.</span><span class="sxs-lookup"><span data-stu-id="0aea9-108">Describes the new ordering of the qubits, where the qubit at index i will now be at ordering[i].</span></span>


### <a name="register--qubit"></a><span data-ttu-id="0aea9-109">Regisztráció: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="0aea9-109">register : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="0aea9-110">A Qubit-regisztrációt kell követni.</span><span class="sxs-lookup"><span data-stu-id="0aea9-110">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0aea9-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0aea9-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

