---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: fd5569f1b71ac2fdf2b5c08ba7dde172e3a6744e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845588"
---
# <a name="mostandtail-function"></a><span data-ttu-id="62c38-102">MostAndTail függvény</span><span class="sxs-lookup"><span data-stu-id="62c38-102">MostAndTail function</span></span>

<span data-ttu-id="62c38-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="62c38-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="62c38-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="62c38-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="62c38-105">A tömb összes, de utolsó elemének egy rekordját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="62c38-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="62c38-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="62c38-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="62c38-107">tömb: "A []</span><span class="sxs-lookup"><span data-stu-id="62c38-107">array : 'A[]</span></span>

<span data-ttu-id="62c38-108">Legalább egy elemet tartalmazó tömb.</span><span class="sxs-lookup"><span data-stu-id="62c38-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="62c38-109">Kimenet: ("A []," A)</span><span class="sxs-lookup"><span data-stu-id="62c38-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="62c38-110">A tömb összes, de utolsó elemének egy rekordja.</span><span class="sxs-lookup"><span data-stu-id="62c38-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="62c38-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="62c38-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="62c38-112">"A</span><span class="sxs-lookup"><span data-stu-id="62c38-112">'A</span></span>

<span data-ttu-id="62c38-113">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="62c38-113">The type of the array elements.</span></span>