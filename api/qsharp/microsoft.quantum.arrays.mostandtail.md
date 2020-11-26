---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 392efb20e4aaba80a77664444bb415d8bc9b0930
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220569"
---
# <a name="mostandtail-function"></a><span data-ttu-id="2880f-102">MostAndTail függvény</span><span class="sxs-lookup"><span data-stu-id="2880f-102">MostAndTail function</span></span>

<span data-ttu-id="2880f-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2880f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2880f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2880f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2880f-105">A tömb összes, de utolsó elemének egy rekordját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2880f-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="2880f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2880f-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="2880f-107">tömb: "A []</span><span class="sxs-lookup"><span data-stu-id="2880f-107">array : 'A[]</span></span>

<span data-ttu-id="2880f-108">Legalább egy elemet tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="2880f-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="2880f-109">Kimenet: ("A []," A)</span><span class="sxs-lookup"><span data-stu-id="2880f-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="2880f-110">A tömb összes, de utolsó elemének egy rekordja.</span><span class="sxs-lookup"><span data-stu-id="2880f-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2880f-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2880f-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="2880f-112">"A</span><span class="sxs-lookup"><span data-stu-id="2880f-112">'A</span></span>

<span data-ttu-id="2880f-113">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="2880f-113">The type of the array elements.</span></span>