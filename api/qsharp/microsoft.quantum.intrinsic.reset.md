---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Visszaállítási művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: b4275796b966bfe7f55271f4e92866410a14e830
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818632"
---
# <a name="reset-operation"></a><span data-ttu-id="eddd1-102">Visszaállítási művelet</span><span class="sxs-lookup"><span data-stu-id="eddd1-102">Reset operation</span></span>

<span data-ttu-id="eddd1-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="eddd1-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="eddd1-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="eddd1-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="eddd1-105">Egyetlen qubit esetén a méri azt, és gondoskodik róla, hogy a (z) | 0 ⟩ állapotban legyen, hogy biztonságosan kiszabadítható legyen.</span><span class="sxs-lookup"><span data-stu-id="eddd1-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="eddd1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="eddd1-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="eddd1-107">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="eddd1-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="eddd1-108">Az a qubit, amelynek az állapotát vissza kell állítani a $ \ket $ értékre {0} .</span><span class="sxs-lookup"><span data-stu-id="eddd1-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eddd1-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eddd1-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

