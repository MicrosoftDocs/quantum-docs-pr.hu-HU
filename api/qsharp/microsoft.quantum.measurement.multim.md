---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: c39601f3e8b272b9341f1789b4c8e7230cb4182c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226995"
---
# <a name="multim-operation"></a><span data-ttu-id="3fb99-102">MultiM művelet</span><span class="sxs-lookup"><span data-stu-id="3fb99-102">MultiM operation</span></span>

<span data-ttu-id="3fb99-103">Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="3fb99-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="3fb99-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3fb99-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3fb99-105">A standard szintű egy adott tömb mindegyik qubit méri.</span><span class="sxs-lookup"><span data-stu-id="3fb99-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="3fb99-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3fb99-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="3fb99-107">célok: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="3fb99-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="3fb99-108">A mérendő qubits tömbje.</span><span class="sxs-lookup"><span data-stu-id="3fb99-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="3fb99-109">Kimenet: __érvénytelen <Result>__[]</span><span class="sxs-lookup"><span data-stu-id="3fb99-109">Output : __invalid<Result>__[]</span></span>

<span data-ttu-id="3fb99-110">A mérési eredmények tömbje.</span><span class="sxs-lookup"><span data-stu-id="3fb99-110">An array of measurement results.</span></span>