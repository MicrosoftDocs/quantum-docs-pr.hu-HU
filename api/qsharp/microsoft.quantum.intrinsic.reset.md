---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Visszaállítási művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: 61b5e4ccdf009dcb6c639e3d8e23bc73a6e475b5
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198673"
---
# <a name="reset-operation"></a><span data-ttu-id="f5d7a-102">Visszaállítási művelet</span><span class="sxs-lookup"><span data-stu-id="f5d7a-102">Reset operation</span></span>

<span data-ttu-id="f5d7a-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="f5d7a-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="f5d7a-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f5d7a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f5d7a-105">Egyetlen qubit esetén a méri azt, és gondoskodik róla, hogy a (z) | 0 ⟩ állapotban legyen, hogy biztonságosan kiszabadítható legyen.</span><span class="sxs-lookup"><span data-stu-id="f5d7a-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="f5d7a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f5d7a-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="f5d7a-107">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f5d7a-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f5d7a-108">Az a qubit, amelynek az állapotát vissza kell állítani a $ \ket $ értékre {0} .</span><span class="sxs-lookup"><span data-stu-id="f5d7a-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f5d7a-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f5d7a-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

