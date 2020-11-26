---
uid: Microsoft.Quantum.Canon.ApplyMultiplyControlledLowDepthAnd
title: ApplyMultiplyControlledLowDepthAnd művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyMultiplyControlledLowDepthAnd
qsharp.summary: Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.  The adjoint operation assumes that the target qubit will be reset to 0.  Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.
ms.openlocfilehash: 1aeab429bd6304c621e0d5225b43a76eab607c84
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209196"
---
# <a name="applymultiplycontrolledlowdepthand-operation"></a><span data-ttu-id="77b01-102">ApplyMultiplyControlledLowDepthAnd művelet</span><span class="sxs-lookup"><span data-stu-id="77b01-102">ApplyMultiplyControlledLowDepthAnd operation</span></span>

<span data-ttu-id="77b01-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="77b01-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="77b01-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="77b01-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="77b01-105">Több vezérelt Toffoli-kaput valósít meg, feltéve, hogy a cél qubit inicializálása 0.</span><span class="sxs-lookup"><span data-stu-id="77b01-105">Implements a multiple-controlled Toffoli gate, assuming that target qubit is initialized 0.</span></span>  <span data-ttu-id="77b01-106">A adjoint művelet azt feltételezi, hogy a cél qubit 0-ra lesz visszaállítva.</span><span class="sxs-lookup"><span data-stu-id="77b01-106">The adjoint operation assumes that the target qubit will be reset to 0.</span></span>  <span data-ttu-id="77b01-107">Az 1. számú rz mélységet igényel, míg a segítő qubits száma exponenciális a qubits száma szerint.</span><span class="sxs-lookup"><span data-stu-id="77b01-107">Requires a Rz depth of 1, while the number of helper qubits are exponential in the number of qubits.</span></span>

```qsharp
operation ApplyMultiplyControlledLowDepthAnd (controls : Qubit[], target : Qubit) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="77b01-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="77b01-108">Input</span></span>

### <a name="controls--qubit"></a><span data-ttu-id="77b01-109">vezérlők: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="77b01-109">controls : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="77b01-110">Qubits vezérlése</span><span class="sxs-lookup"><span data-stu-id="77b01-110">Control qubits</span></span>


### <a name="target--qubit"></a><span data-ttu-id="77b01-111">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="77b01-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="77b01-112">Cél qubit</span><span class="sxs-lookup"><span data-stu-id="77b01-112">Target qubit</span></span>



## <a name="output--unit"></a><span data-ttu-id="77b01-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="77b01-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

