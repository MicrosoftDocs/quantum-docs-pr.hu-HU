---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719177"
---
# <a name="headandrest-function"></a><span data-ttu-id="20b79-102">HeadAndRest függvény</span><span class="sxs-lookup"><span data-stu-id="20b79-102">HeadAndRest function</span></span>

<span data-ttu-id="20b79-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="20b79-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="20b79-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="20b79-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="20b79-105">Az első és a tömb összes többi elemének egy rekordját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="20b79-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="20b79-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="20b79-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="20b79-107">tömb: "A []</span><span class="sxs-lookup"><span data-stu-id="20b79-107">array : 'A[]</span></span>

<span data-ttu-id="20b79-108">Legalább egy elemet tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="20b79-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="20b79-109">Kimenet: ("A", "A []"</span><span class="sxs-lookup"><span data-stu-id="20b79-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="20b79-110">A tömb első és összes többi elemének egy rekordja.</span><span class="sxs-lookup"><span data-stu-id="20b79-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="20b79-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="20b79-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="20b79-112">"A</span><span class="sxs-lookup"><span data-stu-id="20b79-112">'A</span></span>

<span data-ttu-id="20b79-113">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="20b79-113">The type of the array elements.</span></span>