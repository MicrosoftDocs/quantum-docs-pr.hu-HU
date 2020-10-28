---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: ResetAll művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: 00b7c0f508d76fb0f5b46c7ec00c0718469365a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711414"
---
# <a name="resetall-operation"></a><span data-ttu-id="2e123-102">ResetAll művelet</span><span class="sxs-lookup"><span data-stu-id="2e123-102">ResetAll operation</span></span>

<span data-ttu-id="2e123-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="2e123-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="2e123-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2e123-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2e123-105">A qubits egy tömbje, amely méri őket, és gondoskodik arról, hogy a (z) | 0 ⟩ állapotban legyenek, így biztonságosan közzétehetők.</span><span class="sxs-lookup"><span data-stu-id="2e123-105">Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.</span></span>

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2e123-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2e123-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="2e123-107">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="2e123-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="2e123-108">Azon qubits tömbje, amelynek állapotait vissza kell állítani a $ \ket $ értékre {0} .</span><span class="sxs-lookup"><span data-stu-id="2e123-108">An array of qubits whose states are to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2e123-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2e123-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

