---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Interleaved függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 8405cabca17f2dd7c2680833bfab5c3768fcf752
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719141"
---
# <a name="interleaved-function"></a><span data-ttu-id="4d3d3-102">Interleaved függvény</span><span class="sxs-lookup"><span data-stu-id="4d3d3-102">Interleaved function</span></span>

<span data-ttu-id="4d3d3-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4d3d3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4d3d3-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4d3d3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4d3d3-105">Két tömb (majdnem) egyazon méretének együttes elhagyása.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="4d3d3-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="4d3d3-106">Description</span></span>

<span data-ttu-id="4d3d3-107">Ez a függvény két tömb összekapcsolását adja vissza, kezdve az első tömb első elemével, a második tömb első elemével és így tovább.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="4d3d3-108">Az első tömbnek ugyanolyan hosszúságú kell lennie, mint a másodiknak, vagy rendelkezhet még egy elemmel.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="4d3d3-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4d3d3-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="4d3d3-110">első: 'T []</span><span class="sxs-lookup"><span data-stu-id="4d3d3-110">first : 'T[]</span></span>

<span data-ttu-id="4d3d3-111">Az első elhagyni kívánt tömb.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="4d3d3-112">második: 'T []</span><span class="sxs-lookup"><span data-stu-id="4d3d3-112">second : 'T[]</span></span>

<span data-ttu-id="4d3d3-113">Az összekapcsolni kívánt második tömb.</span><span class="sxs-lookup"><span data-stu-id="4d3d3-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="4d3d3-114">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="4d3d3-114">Output : 'T[]</span></span>

<span data-ttu-id="4d3d3-115">Átfedésben lévő tömb</span><span class="sxs-lookup"><span data-stu-id="4d3d3-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4d3d3-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="4d3d3-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4d3d3-117">Nem</span><span class="sxs-lookup"><span data-stu-id="4d3d3-117">'T</span></span>

<span data-ttu-id="4d3d3-118">A és a egyes elemeinek `first` típusa `second` .</span><span class="sxs-lookup"><span data-stu-id="4d3d3-118">The type of each element of `first` and `second`.</span></span>