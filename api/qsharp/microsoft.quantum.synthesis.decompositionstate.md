---
uid: Microsoft.Quantum.Synthesis.DecompositionState
title: DecompositionState-felhasználó által definiált típus
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecompositionState
qsharp.summary: State during decomposition based on variable indexes
ms.openlocfilehash: cd2a55013f1232d4158dd6c33143b7cf6c0aafbc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203195"
---
# <a name="decompositionstate-user-defined-type"></a><span data-ttu-id="eb9c4-102">DecompositionState-felhasználó által definiált típus</span><span class="sxs-lookup"><span data-stu-id="eb9c4-102">DecompositionState user defined type</span></span>

<span data-ttu-id="eb9c4-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="eb9c4-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="eb9c4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eb9c4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eb9c4-105">Állapot a változó indexek alapján történő bontás során</span><span class="sxs-lookup"><span data-stu-id="eb9c4-105">State during decomposition based on variable indexes</span></span>

```qsharp

newtype DecompositionState = (Perm : Int[], Lfunctions : (BigInt, Int)[], Rfunctions : (BigInt, Int)[]);
```



## <a name="named-items"></a><span data-ttu-id="eb9c4-106">Megnevezett elemek</span><span class="sxs-lookup"><span data-stu-id="eb9c4-106">Named Items</span></span>

### <a name="perm--int"></a><span data-ttu-id="eb9c4-107">Dauer: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="eb9c4-107">Perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>


### <a name="lfunctions--bigintint"></a><span data-ttu-id="eb9c4-108">Lfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="eb9c4-108">Lfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>


### <a name="rfunctions--bigintint"></a><span data-ttu-id="eb9c4-109">Rfunctions: ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="eb9c4-109">Rfunctions : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>



## <a name="description"></a><span data-ttu-id="eb9c4-110">Leírás</span><span class="sxs-lookup"><span data-stu-id="eb9c4-110">Description</span></span>

<span data-ttu-id="eb9c4-111">Az állapot tartalmazza az aktuális permutációt és a jelenleg létrehozott függvényeket a bal oldali vezérelt kapuk, valamint a jobb oldalon található vezérelt kapuk.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-111">The state holds the current permutation and the currently generated functions for controlled gates on the left, and controlled gates on the right.</span></span>