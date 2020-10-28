---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 6900f9b0f014fba28ae73a70f180f3e4696900cd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92717952"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="bbe3d-102">ApplyMultiplyControlledLowDepthAnd művelet</span><span class="sxs-lookup"><span data-stu-id="bbe3d-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="bbe3d-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bbe3d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bbe3d-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bbe3d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bbe3d-105">Több vezérelt Toffoli-kaput valósít meg, feltéve, hogy a cél qubit inicializálása 0.</span><span class="sxs-lookup"><span data-stu-id="bbe3d-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="bbe3d-106">A adjoint művelet azt feltételezi, hogy a cél qubit 0-ra lesz visszaállítva.</span><span class="sxs-lookup"><span data-stu-id="bbe3d-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="bbe3d-107">Az 1. számú rz mélységet igényel, míg a segítő qubits száma exponenciális a qubits száma szerint.</span><span class="sxs-lookup"><span data-stu-id="bbe3d-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="bbe3d-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bbe3d-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="bbe3d-109">vezérlők: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="bbe3d-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="bbe3d-110">Qubits vezérlése</span><span class="sxs-lookup"><span data-stu-id="bbe3d-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="bbe3d-111">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bbe3d-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bbe3d-112">Cél qubit</span><span class="sxs-lookup"><span data-stu-id="bbe3d-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="bbe3d-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bbe3d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

