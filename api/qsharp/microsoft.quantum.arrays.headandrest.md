---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848550"
---
# <a name="headandrest-function"></a><span data-ttu-id="e280c-102">HeadAndRest függvény</span><span class="sxs-lookup"><span data-stu-id="e280c-102">HeadAndRest function</span></span>

<span data-ttu-id="e280c-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e280c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e280c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e280c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e280c-105">Az első és a tömb összes többi elemének egy rekordját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="e280c-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="e280c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e280c-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="e280c-107">tömb: "A []</span><span class="sxs-lookup"><span data-stu-id="e280c-107">array : 'A[]</span></span>

<span data-ttu-id="e280c-108">Legalább egy elemet tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="e280c-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="e280c-109">Kimenet: ("A", "A []"</span><span class="sxs-lookup"><span data-stu-id="e280c-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="e280c-110">A tömb első és összes többi elemének egy rekordja.</span><span class="sxs-lookup"><span data-stu-id="e280c-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e280c-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e280c-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="e280c-112">"A</span><span class="sxs-lookup"><span data-stu-id="e280c-112">'A</span></span>

<span data-ttu-id="e280c-113">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="e280c-113">The type of the array elements.</span></span>