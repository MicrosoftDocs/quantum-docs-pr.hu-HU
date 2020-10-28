---
uid: Microsoft.Quantum.Intrinsic.I
title: I művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 555f714047a38f49ccd94a77dc14a46d6f4988ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720028"
---
# <a name="i-operation"></a><span data-ttu-id="1bcf6-102">I művelet</span><span class="sxs-lookup"><span data-stu-id="1bcf6-102">I operation</span></span>

<span data-ttu-id="1bcf6-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="1bcf6-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="1bcf6-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1bcf6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1bcf6-105">Végrehajtja az Identity műveletet (No-op) egyetlen qubit.</span><span class="sxs-lookup"><span data-stu-id="1bcf6-105">Performs the identity operation (no-op) on a single qubit.</span></span>

```qsharp
operation I (target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="1bcf6-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1bcf6-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="1bcf6-107">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1bcf6-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="1bcf6-108">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1bcf6-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1bcf6-109">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="1bcf6-109">Remarks</span></span>

<span data-ttu-id="1bcf6-110">Ez egy nem-op.</span><span class="sxs-lookup"><span data-stu-id="1bcf6-110">This is a no-op.</span></span> <span data-ttu-id="1bcf6-111">A teljességhez van megadva, és mivel időnként hasznos lehet az identitás meghívása egy algoritmusban, vagy paraméterként való továbbítása.</span><span class="sxs-lookup"><span data-stu-id="1bcf6-111">It is provided for completeness and because sometimes it is useful to call the identity in an algorithm or to pass it as a parameter.</span></span>