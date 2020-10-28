---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 8786250cf2f78ce2e9ff8baddc856d0bc07cb9a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718996"
---
# <a name="mostandtail-function"></a><span data-ttu-id="50be2-102">MostAndTail függvény</span><span class="sxs-lookup"><span data-stu-id="50be2-102">MostAndTail function</span></span>

<span data-ttu-id="50be2-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="50be2-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="50be2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="50be2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="50be2-105">A tömb összes, de utolsó elemének egy rekordját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="50be2-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="50be2-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="50be2-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="50be2-107">tömb: "A []</span><span class="sxs-lookup"><span data-stu-id="50be2-107">array : 'A[]</span></span>

<span data-ttu-id="50be2-108">Legalább egy elemet tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="50be2-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="50be2-109">Kimenet: ("A []," A)</span><span class="sxs-lookup"><span data-stu-id="50be2-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="50be2-110">A tömb összes, de utolsó elemének egy rekordja.</span><span class="sxs-lookup"><span data-stu-id="50be2-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="50be2-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="50be2-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="50be2-112">"A</span><span class="sxs-lookup"><span data-stu-id="50be2-112">'A</span></span>

<span data-ttu-id="50be2-113">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="50be2-113">The type of the array elements.</span></span>