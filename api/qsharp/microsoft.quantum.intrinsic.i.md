---
uid: Microsoft.Quantum.Intrinsic.I
title: I művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: I
qsharp.summary: Performs the identity operation (no-op) on a single qubit.
ms.openlocfilehash: 0af14a9aff20da493e95c7feba6afbb907d3d69f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849412"
---
# <a name="i-operation"></a><span data-ttu-id="5f974-102">I művelet</span><span class="sxs-lookup"><span data-stu-id="5f974-102">I operation</span></span>

<span data-ttu-id="5f974-103">Névtér: [Microsoft. Quantum. belső](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="5f974-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="5f974-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="5f974-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="5f974-105">Végrehajtja az Identity műveletet (No-op) egyetlen qubit.</span><span class="sxs-lookup"><span data-stu-id="5f974-105">Performs the identity operation (no-op) on a single qubit.</span></span>

```qsharp
operation I (target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="5f974-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5f974-106">Input</span></span>

### <a name="target--qubit"></a><span data-ttu-id="5f974-107">cél: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="5f974-107">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>





## <a name="output--unit"></a><span data-ttu-id="5f974-108">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5f974-108">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5f974-109">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="5f974-109">Remarks</span></span>

<span data-ttu-id="5f974-110">Ez egy nem-op.</span><span class="sxs-lookup"><span data-stu-id="5f974-110">This is a no-op.</span></span> <span data-ttu-id="5f974-111">A teljességhez van megadva, és mivel időnként hasznos lehet az identitás meghívása egy algoritmusban, vagy paraméterként való továbbítása.</span><span class="sxs-lookup"><span data-stu-id="5f974-111">It is provided for completeness and because sometimes it is useful to call the identity in an algorithm or to pass it as a parameter.</span></span>