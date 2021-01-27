---
uid: Microsoft.Quantum.Arrays.Interleaved
title: Interleaved függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848116"
---
# <a name="interleaved-function"></a><span data-ttu-id="03613-102">Interleaved függvény</span><span class="sxs-lookup"><span data-stu-id="03613-102">Interleaved function</span></span>

<span data-ttu-id="03613-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="03613-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="03613-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="03613-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="03613-105">Két tömb (majdnem) egyazon méretének együttes elhagyása.</span><span class="sxs-lookup"><span data-stu-id="03613-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="03613-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="03613-106">Description</span></span>

<span data-ttu-id="03613-107">Ez a függvény két tömb összekapcsolását adja vissza, kezdve az első tömb első elemével, a második tömb első elemével és így tovább.</span><span class="sxs-lookup"><span data-stu-id="03613-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="03613-108">Az első tömbnek ugyanolyan hosszúságú kell lennie, mint a másodiknak, vagy rendelkezhet még egy elemmel.</span><span class="sxs-lookup"><span data-stu-id="03613-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="03613-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="03613-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="03613-110">első: 'T []</span><span class="sxs-lookup"><span data-stu-id="03613-110">first : 'T[]</span></span>

<span data-ttu-id="03613-111">Az első elhagyni kívánt tömb.</span><span class="sxs-lookup"><span data-stu-id="03613-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="03613-112">második: 'T []</span><span class="sxs-lookup"><span data-stu-id="03613-112">second : 'T[]</span></span>

<span data-ttu-id="03613-113">Az összekapcsolni kívánt második tömb.</span><span class="sxs-lookup"><span data-stu-id="03613-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="03613-114">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="03613-114">Output : 'T[]</span></span>

<span data-ttu-id="03613-115">Átfedésben lévő tömb</span><span class="sxs-lookup"><span data-stu-id="03613-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="03613-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="03613-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="03613-117">Nem</span><span class="sxs-lookup"><span data-stu-id="03613-117">'T</span></span>

<span data-ttu-id="03613-118">A és a egyes elemeinek `first` típusa `second` .</span><span class="sxs-lookup"><span data-stu-id="03613-118">The type of each element of `first` and `second`.</span></span>

## <a name="example"></a><span data-ttu-id="03613-119">Példa</span><span class="sxs-lookup"><span data-stu-id="03613-119">Example</span></span>

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```