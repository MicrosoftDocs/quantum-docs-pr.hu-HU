---
uid: Microsoft.Quantum.Arrays.Exclude
title: Funkció kizárása
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 76cdee56e84951c63e80babfdca6a3de33583cab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848679"
---
# <a name="exclude-function"></a><span data-ttu-id="e0621-102">Funkció kizárása</span><span class="sxs-lookup"><span data-stu-id="e0621-102">Exclude function</span></span>

<span data-ttu-id="e0621-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e0621-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e0621-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e0621-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e0621-105">Egy olyan tömböt ad vissza, amely egy másik tömb elemeit tartalmazza, és az indexek adott listáján szereplő elemeket is kizárja.</span><span class="sxs-lookup"><span data-stu-id="e0621-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e0621-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e0621-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="e0621-107">eltávolítás: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e0621-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e0621-108">Az indexek tömbje, amely azt jelöli, hogy mely elemeket kell kizárni a kimenetből.</span><span class="sxs-lookup"><span data-stu-id="e0621-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="e0621-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="e0621-109">array : 'T[]</span></span>

<span data-ttu-id="e0621-110">Az a tömb, amely a kimeneti tömbben szereplő értékeket veszi fel.</span><span class="sxs-lookup"><span data-stu-id="e0621-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="e0621-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="e0621-111">Output : 'T[]</span></span>

<span data-ttu-id="e0621-112">Egy olyan tömb `output` `output[0]` , amely az első eleme, `array` amelynek az indexe nem jelenik meg `remove` , például `output[1]` a második ilyen elem, és így tovább.</span><span class="sxs-lookup"><span data-stu-id="e0621-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e0621-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e0621-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e0621-114">Nem</span><span class="sxs-lookup"><span data-stu-id="e0621-114">'T</span></span>

<span data-ttu-id="e0621-115">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="e0621-115">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="e0621-116">Példa</span><span class="sxs-lookup"><span data-stu-id="e0621-116">Example</span></span>

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Exclude([1, 3, 4], array);
```