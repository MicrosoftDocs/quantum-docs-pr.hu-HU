---
uid: Microsoft.Quantum.Measurement.MultiM
title: MultiM művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: MultiM
qsharp.summary: Measures each qubit in a given array in the standard basis.
ms.openlocfilehash: 36de9dbdfc96f6e1698ee4537405f7cb74e44262
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711037"
---
# <a name="multim-operation"></a><span data-ttu-id="9f657-102">MultiM művelet</span><span class="sxs-lookup"><span data-stu-id="9f657-102">MultiM operation</span></span>

<span data-ttu-id="9f657-103">Névtér: [Microsoft. Quantum. mérés](xref:Microsoft.Quantum.Measurement)</span><span class="sxs-lookup"><span data-stu-id="9f657-103">Namespace: [Microsoft.Quantum.Measurement](xref:Microsoft.Quantum.Measurement)</span></span>

<span data-ttu-id="9f657-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9f657-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9f657-105">A standard szintű egy adott tömb mindegyik qubit méri.</span><span class="sxs-lookup"><span data-stu-id="9f657-105">Measures each qubit in a given array in the standard basis.</span></span>

```qsharp
operation MultiM (targets : Qubit[]) : Result[]
```


## <a name="input"></a><span data-ttu-id="9f657-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9f657-106">Input</span></span>

### <a name="targets--qubit"></a><span data-ttu-id="9f657-107">célok: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="9f657-107">targets : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="9f657-108">A mérendő qubits tömbje.</span><span class="sxs-lookup"><span data-stu-id="9f657-108">An array of qubits to be measured.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="9f657-109">Kimenet: __érvénytelen <Result>__ []</span><span class="sxs-lookup"><span data-stu-id="9f657-109">Output : __invalid<Result>__ []</span></span>

<span data-ttu-id="9f657-110">A mérési eredmények tömbje.</span><span class="sxs-lookup"><span data-stu-id="9f657-110">An array of measurement results.</span></span>