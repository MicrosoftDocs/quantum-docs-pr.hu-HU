---
uid: Microsoft.Quantum.Arrays.Flattened
title: Összeolvasztott függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Flattened
qsharp.summary: Given an array of arrays, returns the concatenation of all arrays.
ms.openlocfilehash: 272533d4efd8598b21daa341c867c070a2083ce0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848620"
---
# <a name="flattened-function"></a><span data-ttu-id="b28c6-102">Összeolvasztott függvény</span><span class="sxs-lookup"><span data-stu-id="b28c6-102">Flattened function</span></span>

<span data-ttu-id="b28c6-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b28c6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b28c6-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b28c6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b28c6-105">A tömbök tömbje az összes tömb összefűzését adja vissza.</span><span class="sxs-lookup"><span data-stu-id="b28c6-105">Given an array of arrays, returns the concatenation of all arrays.</span></span>

```qsharp
function Flattened<'T> (arrays : 'T[][]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="b28c6-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b28c6-106">Input</span></span>

### <a name="arrays--t"></a><span data-ttu-id="b28c6-107">tömbök: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="b28c6-107">arrays : 'T[][]</span></span>

<span data-ttu-id="b28c6-108">Tömbök tömbje.</span><span class="sxs-lookup"><span data-stu-id="b28c6-108">Array of arrays.</span></span>



## <a name="output--t"></a><span data-ttu-id="b28c6-109">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="b28c6-109">Output : 'T[]</span></span>

<span data-ttu-id="b28c6-110">Az összes tömb összefűzése.</span><span class="sxs-lookup"><span data-stu-id="b28c6-110">Concatenation of all arrays.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b28c6-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="b28c6-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b28c6-112">Nem</span><span class="sxs-lookup"><span data-stu-id="b28c6-112">'T</span></span>

<span data-ttu-id="b28c6-113">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="b28c6-113">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="b28c6-114">Példa</span><span class="sxs-lookup"><span data-stu-id="b28c6-114">Example</span></span>

```qsharp
let flattened = Flattened([[1, 2], [3], [4, 5, 6]]);
// flattened = [1, 2, 3, 4, 5, 6]
```