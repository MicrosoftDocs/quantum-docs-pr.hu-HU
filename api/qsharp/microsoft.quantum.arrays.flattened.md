---
uid: Microsoft.Quantum.Arrays.Flattened
title: Összeolvasztott függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 331b1714109259b21982e99d030aa0662e3aaadb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221215"
---
# <a name="flattened-function"></a><span data-ttu-id="69335-102">Összeolvasztott függvény</span><span class="sxs-lookup"><span data-stu-id="69335-102">Flattened function</span></span>

<span data-ttu-id="69335-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="69335-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="69335-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69335-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69335-105">A tömbök tömbje az összes tömb összefűzését adja vissza.</span><span class="sxs-lookup"><span data-stu-id="69335-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="69335-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="69335-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="69335-107">tömbök: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="69335-107">arrays : 'T[][]</span></span>

<span data-ttu-id="69335-108">Tömbök tömbje.</span><span class="sxs-lookup"><span data-stu-id="69335-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="69335-109">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="69335-109">Output : 'T[]</span></span>

<span data-ttu-id="69335-110">Az összes tömb összefűzése.</span><span class="sxs-lookup"><span data-stu-id="69335-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="69335-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="69335-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="69335-112">Nem</span><span class="sxs-lookup"><span data-stu-id="69335-112">'T</span></span>

<span data-ttu-id="69335-113">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="69335-113">The type of `array` elements.</span></span>