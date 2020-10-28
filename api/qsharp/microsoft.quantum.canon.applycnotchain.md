---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: ApplyCNOTChain művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: c98fe24ca352952162acb7a9c4fc93d5da4285b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718373"
---
# <a name="applycnotchain-operation"></a><span data-ttu-id="8b556-102">ApplyCNOTChain művelet</span><span class="sxs-lookup"><span data-stu-id="8b556-102">ApplyCNOTChain operation</span></span>

<span data-ttu-id="8b556-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8b556-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8b556-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8b556-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8b556-105">Kiszámítja a qubits-regisztráció paritását.</span><span class="sxs-lookup"><span data-stu-id="8b556-105">Computes the parity of a register of qubits in-place.</span></span>

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit
```


## <a name="description"></a><span data-ttu-id="8b556-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="8b556-106">Description</span></span>

<span data-ttu-id="8b556-107">Ez a művelet átalakítja a bemenetének állapotát $ $ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_ {n-1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus Q_ {n-1}}.</span><span class="sxs-lookup"><span data-stu-id="8b556-107">This operation transforms the state of its input as $$ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_{n - 1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_{n - 1}}.</span></span>
<span data-ttu-id="8b556-108">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="8b556-108">\end{align} $$</span></span>

## <a name="input"></a><span data-ttu-id="8b556-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8b556-109">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="8b556-110">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="8b556-110">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="8b556-111">Azon qubits tömbje, amelynek paritását számításba kell venni és tárolni kell.</span><span class="sxs-lookup"><span data-stu-id="8b556-111">Array of qubits whose parity is to be computed and stored.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8b556-112">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8b556-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

