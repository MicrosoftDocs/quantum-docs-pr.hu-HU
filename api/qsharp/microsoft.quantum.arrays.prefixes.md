---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Előtagok függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 3501c11437534b1623bffba272a4517487e5634a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220388"
---
# <a name="prefixes-function"></a><span data-ttu-id="e32eb-102">Előtagok függvény</span><span class="sxs-lookup"><span data-stu-id="e32eb-102">Prefixes function</span></span>

<span data-ttu-id="e32eb-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e32eb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e32eb-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e32eb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e32eb-105">A tömb megadott értéke az összes előtagjait adja vissza.</span><span class="sxs-lookup"><span data-stu-id="e32eb-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="e32eb-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="e32eb-106">Description</span></span>

<span data-ttu-id="e32eb-107">Az összes előtag tömbjét adja vissza, amely egy olyan tömbtől kezdődik, amely csak az első elemet tartalmazza, amíg a teljes tömb be nem fejeződik.</span><span class="sxs-lookup"><span data-stu-id="e32eb-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="e32eb-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e32eb-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="e32eb-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="e32eb-109">array : 'T[]</span></span>

<span data-ttu-id="e32eb-110">Elemek tömbje.</span><span class="sxs-lookup"><span data-stu-id="e32eb-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="e32eb-111">Kimenet: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="e32eb-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e32eb-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e32eb-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e32eb-113">Nem</span><span class="sxs-lookup"><span data-stu-id="e32eb-113">'T</span></span>

<span data-ttu-id="e32eb-114">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="e32eb-114">The type of `array` elements.</span></span>