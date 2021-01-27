---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: ResetAll művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: 2b8e7fc0e7881d8c1bd6f14c150476262b7a2b19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849318"
---
# <a name="resetall-operation"></a><span data-ttu-id="62839-102">ResetAll művelet</span><span class="sxs-lookup"><span data-stu-id="62839-102">ResetAll operation</span></span>

<span data-ttu-id="62839-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="62839-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="62839-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="62839-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="62839-105">A qubits egy tömbje, amely méri őket, és gondoskodik arról, hogy a (z) | 0 ⟩ állapotban legyenek, így biztonságosan közzétehetők.</span><span class="sxs-lookup"><span data-stu-id="62839-105">Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.</span></span>

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="62839-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="62839-106">Input</span></span>

### <a name="qubits--qubit"></a><span data-ttu-id="62839-107">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="62839-107">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="62839-108">Azon qubits tömbje, amelynek állapotait vissza kell állítani a $ \ket $ értékre {0} .</span><span class="sxs-lookup"><span data-stu-id="62839-108">An array of qubits whose states are to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="62839-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="62839-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

