---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 0ad4b6eabcbbb63751489dd92a13a6673c1ae6b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841677"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="69b0c-102">ApplyMultiplyControlledLowDepthAnd művelet</span><span class="sxs-lookup"><span data-stu-id="69b0c-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="69b0c-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="69b0c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="69b0c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69b0c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69b0c-105">Több vezérelt Toffoli-kaput valósít meg, feltéve, hogy a cél qubit inicializálása 0.</span><span class="sxs-lookup"><span data-stu-id="69b0c-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="69b0c-106">A adjoint művelet azt feltételezi, hogy a cél qubit 0-ra lesz visszaállítva.</span><span class="sxs-lookup"><span data-stu-id="69b0c-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="69b0c-107">Az 1. számú rz mélységet igényel, míg a segítő qubits száma exponenciális a qubits száma szerint.</span><span class="sxs-lookup"><span data-stu-id="69b0c-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="69b0c-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="69b0c-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="69b0c-109">vezérlők: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="69b0c-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="69b0c-110">Qubits vezérlése</span><span class="sxs-lookup"><span data-stu-id="69b0c-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="69b0c-111">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="69b0c-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="69b0c-112">Cél qubit</span><span class="sxs-lookup"><span data-stu-id="69b0c-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="69b0c-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69b0c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

