---
uid: Microsoft.Quantum.Arrays.Flattened
title: Összeolvasztott függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 91a35f0ac2c2f8609bac07734265fcf4e88bf50b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719237"
---
# <a name="flattened-function"></a><span data-ttu-id="93ce9-102">Összeolvasztott függvény</span><span class="sxs-lookup"><span data-stu-id="93ce9-102">Flattened function</span></span>

<span data-ttu-id="93ce9-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="93ce9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="93ce9-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93ce9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93ce9-105">A tömbök tömbje az összes tömb összefűzését adja vissza.</span><span class="sxs-lookup"><span data-stu-id="93ce9-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="93ce9-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="93ce9-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="93ce9-107">tömbök: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="93ce9-107">arrays : 'T[][]</span></span>

<span data-ttu-id="93ce9-108">Tömbök tömbje.</span><span class="sxs-lookup"><span data-stu-id="93ce9-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="93ce9-109">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="93ce9-109">Output : 'T[]</span></span>

<span data-ttu-id="93ce9-110">Az összes tömb összefűzése.</span><span class="sxs-lookup"><span data-stu-id="93ce9-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="93ce9-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="93ce9-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="93ce9-112">Nem</span><span class="sxs-lookup"><span data-stu-id="93ce9-112">'T</span></span>

<span data-ttu-id="93ce9-113">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="93ce9-113">The type of `array` elements.</span></span>