---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Interleaved függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220960"
---
# <a name="interleaved-function"></a><span data-ttu-id="a04b4-102">Interleaved függvény</span><span class="sxs-lookup"><span data-stu-id="a04b4-102">Interleaved function</span></span>

<span data-ttu-id="a04b4-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a04b4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a04b4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a04b4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a04b4-105">Két tömb (majdnem) egyazon méretének együttes elhagyása.</span><span class="sxs-lookup"><span data-stu-id="a04b4-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="a04b4-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="a04b4-106">Description</span></span>

<span data-ttu-id="a04b4-107">Ez a függvény két tömb összekapcsolását adja vissza, kezdve az első tömb első elemével, a második tömb első elemével és így tovább.</span><span class="sxs-lookup"><span data-stu-id="a04b4-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="a04b4-108">Az első tömbnek ugyanolyan hosszúságú kell lennie, mint a másodiknak, vagy rendelkezhet még egy elemmel.</span><span class="sxs-lookup"><span data-stu-id="a04b4-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="a04b4-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a04b4-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="a04b4-110">első: 'T []</span><span class="sxs-lookup"><span data-stu-id="a04b4-110">first : 'T[]</span></span>

<span data-ttu-id="a04b4-111">Az első elhagyni kívánt tömb.</span><span class="sxs-lookup"><span data-stu-id="a04b4-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="a04b4-112">második: 'T []</span><span class="sxs-lookup"><span data-stu-id="a04b4-112">second : 'T[]</span></span>

<span data-ttu-id="a04b4-113">Az összekapcsolni kívánt második tömb.</span><span class="sxs-lookup"><span data-stu-id="a04b4-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="a04b4-114">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="a04b4-114">Output : 'T[]</span></span>

<span data-ttu-id="a04b4-115">Átfedésben lévő tömb</span><span class="sxs-lookup"><span data-stu-id="a04b4-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a04b4-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="a04b4-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a04b4-117">Nem</span><span class="sxs-lookup"><span data-stu-id="a04b4-117">'T</span></span>

<span data-ttu-id="a04b4-118">A és a egyes elemeinek `first` típusa `second` .</span><span class="sxs-lookup"><span data-stu-id="a04b4-118">The type of each element of `first` and `second`.</span></span>