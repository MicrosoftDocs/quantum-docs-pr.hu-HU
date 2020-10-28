---
uid: Microsoft.Quantum.Arrays.Prefixes
title: Előtagok függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Prefixes
qsharp.summary: Given an array, returns all its prefixes.
ms.openlocfilehash: 1576e57e9dc64a605eb65cb841640e72a3b126ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718937"
---
# <a name="prefixes-function"></a><span data-ttu-id="50dad-102">Előtagok függvény</span><span class="sxs-lookup"><span data-stu-id="50dad-102">Prefixes function</span></span>

<span data-ttu-id="50dad-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="50dad-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="50dad-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50dad-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50dad-105">A tömb megadott értéke az összes előtagjait adja vissza.</span><span class="sxs-lookup"><span data-stu-id="50dad-105">Given an array, returns all its prefixes.</span></span>

```qsharp
function Prefixes<'T> (array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="50dad-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="50dad-106">Description</span></span>

<span data-ttu-id="50dad-107">Az összes előtag tömbjét adja vissza, amely egy olyan tömbtől kezdődik, amely csak az első elemet tartalmazza, amíg a teljes tömb be nem fejeződik.</span><span class="sxs-lookup"><span data-stu-id="50dad-107">Returns an array of all prefixes, starting with an array that only has the first element until the complete array.</span></span>

## <a name="input"></a><span data-ttu-id="50dad-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="50dad-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="50dad-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="50dad-109">array : 'T[]</span></span>

<span data-ttu-id="50dad-110">Elemek tömbje.</span><span class="sxs-lookup"><span data-stu-id="50dad-110">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="50dad-111">Kimenet: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="50dad-111">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="50dad-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="50dad-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="50dad-113">Nem</span><span class="sxs-lookup"><span data-stu-id="50dad-113">'T</span></span>

<span data-ttu-id="50dad-114">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="50dad-114">The type of `array` elements.</span></span>