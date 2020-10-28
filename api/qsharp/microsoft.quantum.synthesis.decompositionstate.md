---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: DecompositionState-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: 0547c04828a80b4f696cc17e13c8cc57d0379f96
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725209"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="a80df-102">DecompositionState-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="a80df-102">DecompositionState user defined type</span></span>

<span data-ttu-id="a80df-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="a80df-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="a80df-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a80df-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a80df-105">Állapot a változó indexek alapján történő bontás során</span><span class="sxs-lookup"><span data-stu-id="a80df-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="a80df-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="a80df-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="a80df-107">Dauer: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="a80df-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="a80df-108">Lfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="a80df-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="a80df-109">Rfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="a80df-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="a80df-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="a80df-110">Description</span></span>

<span data-ttu-id="a80df-111">Az állapot tartalmazza az aktuális permutációt és a jelenleg létrehozott függvényeket a bal oldali vezérelt kapuk, valamint a jobb oldalon található vezérelt kapuk.</span><span class="sxs-lookup"><span data-stu-id="a80df-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>