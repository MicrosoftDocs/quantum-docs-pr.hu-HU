---
uid: Microsoft.Quantum.Intrinsic.I
title: I művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 5aae7a5e3b5b441829de8f10f4df539ffc374954
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198945"
---
# <a name="i-operation"></a><span data-ttu-id="cfe07-102">I művelet</span><span class="sxs-lookup"><span data-stu-id="cfe07-102">I operation</span></span>

<span data-ttu-id="cfe07-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="cfe07-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="cfe07-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="cfe07-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="cfe07-105">Végrehajtja az Identity műveletet (No-op) egyetlen qubit.</span><span class="sxs-lookup"><span data-stu-id="cfe07-105">Performs the identity operation (no-op) on a single qubit.</span></span>

```qsharp
operation I (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="cfe07-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="cfe07-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="cfe07-107">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="cfe07-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="cfe07-108">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cfe07-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cfe07-109">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="cfe07-109">Remarks</span></span>

<span data-ttu-id="cfe07-110">Ez egy nem-op.</span><span class="sxs-lookup"><span data-stu-id="cfe07-110">This is a no-op.</span></span> <span data-ttu-id="cfe07-111">A teljességhez van megadva, és mivel időnként hasznos lehet az identitás meghívása egy algoritmusban, vagy paraméterként való továbbítása.</span><span class="sxs-lookup"><span data-stu-id="cfe07-111">It is provided for completeness and because sometimes it is useful to call the identity in an algorithm or to pass it as a parameter.</span></span>