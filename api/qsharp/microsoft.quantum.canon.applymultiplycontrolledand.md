---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: ApplyMultiplyControlledAnd művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: 17a757278500833bc5a5d0635af020cfe1fd569f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218393"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="531bb-102">ApplyMultiplyControlledAnd művelet</span><span class="sxs-lookup"><span data-stu-id="531bb-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="531bb-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="531bb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="531bb-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="531bb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="531bb-105">Több vezérelt Toffoli-kaput valósít meg, feltéve, hogy a cél qubit inicializálása 0.</span><span class="sxs-lookup"><span data-stu-id="531bb-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="531bb-106">A adjoint művelet azt feltételezi, hogy a cél qubit 0-ra lesz visszaállítva.</span><span class="sxs-lookup"><span data-stu-id="531bb-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="531bb-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="531bb-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="531bb-108">vezérlők: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="531bb-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="531bb-109">Qubits vezérlése</span><span class="sxs-lookup"><span data-stu-id="531bb-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="531bb-110">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="531bb-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="531bb-111">Cél qubit</span><span class="sxs-lookup"><span data-stu-id="531bb-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="531bb-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="531bb-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

