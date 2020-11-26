---
uid: Microsoft.Quantum.Canon.ApplyAndChain
title: ApplyAndChain művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAndChain
qsharp.summary: Computes a chain of AND gates
ms.openlocfilehash: c53bca6ecf964f4358b0a7ff1c61d4e8e195cd7d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219362"
---
# <a name="applyandchain-operation"></a><span data-ttu-id="453aa-102">ApplyAndChain művelet</span><span class="sxs-lookup"><span data-stu-id="453aa-102">ApplyAndChain operation</span></span>

<span data-ttu-id="453aa-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="453aa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="453aa-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="453aa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="453aa-105">Kiszámítja a láncot és kapukat</span><span class="sxs-lookup"><span data-stu-id="453aa-105">Computes a chain of AND gates</span></span>

```qsharp
operation ApplyAndChain (auxRegister : Qubit[], ctrlRegister : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="453aa-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="453aa-106">Description</span></span>

<span data-ttu-id="453aa-107">Explicit módon meg kell adni a kiszámított ideiglenes eredmények kisegítő qubits.</span><span class="sxs-lookup"><span data-stu-id="453aa-107">The auxiliary qubits to compute temporary results must be specified explicitly.</span></span>
<span data-ttu-id="453aa-108">A regisztráció hossza `Length(ctrlRegister) - 2` , ha legalább két vezérlőelem van, ellenkező esetben a hossz 0.</span><span class="sxs-lookup"><span data-stu-id="453aa-108">The length of that register is `Length(ctrlRegister) - 2`, if there are at least two controls, otherwise the length is 0.</span></span>

## <a name="input"></a><span data-ttu-id="453aa-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="453aa-109">Input</span></span>

### <a name="auxregister--qubit"></a><span data-ttu-id="453aa-110">auxRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="453aa-110">auxRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="ctrlregister--qubit"></a><span data-ttu-id="453aa-111">ctrlRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="453aa-111">ctrlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>




### <a name="target--qubit"></a><span data-ttu-id="453aa-112">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="453aa-112">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="453aa-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="453aa-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

