---
uid: Microsoft.Quantum.Intrinsic.Reset
title: Visszaállítási művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Reset
qsharp.summary: Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.
ms.openlocfilehash: c89cbbce49e294e56abc11b3b0492d2ed8e980a8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720869"
---
# <a name="reset-operation"></a><span data-ttu-id="4b993-102">Visszaállítási művelet</span><span class="sxs-lookup"><span data-stu-id="4b993-102">Reset operation</span></span>

<span data-ttu-id="4b993-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="4b993-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="4b993-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4b993-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4b993-105">Egyetlen qubit esetén a méri azt, és gondoskodik róla, hogy a (z) | 0 ⟩ állapotban legyen, hogy biztonságosan kiszabadítható legyen.</span><span class="sxs-lookup"><span data-stu-id="4b993-105">Given a single qubit, measures it and ensures it is in the |0⟩ state such that it can be safely released.</span></span>

```qsharp
operation Reset (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="4b993-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4b993-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="4b993-107">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4b993-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4b993-108">Az a qubit, amelynek az állapotát vissza kell állítani a $ \ket $ értékre {0} .</span><span class="sxs-lookup"><span data-stu-id="4b993-108">The qubit whose state is to be reset to $\ket{0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4b993-109">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4b993-109">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

