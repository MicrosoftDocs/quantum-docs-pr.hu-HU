---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 1144e00227df1cd7d96bc76b118b0b556adbaa96
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221079"
---
# <a name="headandrest-function"></a><span data-ttu-id="49b4e-102">HeadAndRest függvény</span><span class="sxs-lookup"><span data-stu-id="49b4e-102">HeadAndRest function</span></span>

<span data-ttu-id="49b4e-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="49b4e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="49b4e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="49b4e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="49b4e-105">Az első és a tömb összes többi elemének egy rekordját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="49b4e-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="49b4e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="49b4e-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="49b4e-107">tömb: "A []</span><span class="sxs-lookup"><span data-stu-id="49b4e-107">array : 'A[]</span></span>

<span data-ttu-id="49b4e-108">Legalább egy elemet tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="49b4e-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="49b4e-109">Kimenet: ("A", "A []"</span><span class="sxs-lookup"><span data-stu-id="49b4e-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="49b4e-110">A tömb első és összes többi elemének egy rekordja.</span><span class="sxs-lookup"><span data-stu-id="49b4e-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="49b4e-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="49b4e-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="49b4e-112">"A</span><span class="sxs-lookup"><span data-stu-id="49b4e-112">'A</span></span>

<span data-ttu-id="49b4e-113">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="49b4e-113">The type of the array elements.</span></span>