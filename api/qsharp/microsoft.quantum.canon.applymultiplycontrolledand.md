---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledAnd
title: ApplyMultiplyControlledAnd művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.
ms.openlocfilehash: feca28d394e4af31eb4ffe737111d00ede45e27e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717953"
---
# <a name="applymultiplycontrolledand-operation"></a><span data-ttu-id="ec6a6-102">ApplyMultiplyControlledAnd művelet</span><span class="sxs-lookup"><span data-stu-id="ec6a6-102">ApplyMultiplyControlledAnd operation</span></span>

<span data-ttu-id="ec6a6-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ec6a6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ec6a6-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ec6a6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ec6a6-105">Több vezérelt Toffoli-kaput valósít meg, feltéve, hogy a cél qubit inicializálása 0.</span><span class="sxs-lookup"><span data-stu-id="ec6a6-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="ec6a6-106">A adjoint művelet azt feltételezi, hogy a cél qubit 0-ra lesz visszaállítva.</span><span class="sxs-lookup"><span data-stu-id="ec6a6-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>

```qsharp
operation ApplyMultiplyControlledAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="ec6a6-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ec6a6-107">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="ec6a6-108">vezérlők: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="ec6a6-108">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="ec6a6-109">Qubits vezérlése</span><span class="sxs-lookup"><span data-stu-id="ec6a6-109">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ec6a6-110">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ec6a6-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ec6a6-111">Cél qubit</span><span class="sxs-lookup"><span data-stu-id="ec6a6-111">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="ec6a6-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ec6a6-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

