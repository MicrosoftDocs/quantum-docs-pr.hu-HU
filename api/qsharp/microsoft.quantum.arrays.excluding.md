---
uid: Microsoft.Quantum.Arrays.Excluding
title: Függvény kizárása
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 6585e619834a96953c9eae2d36a8ebe0a11dbda0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221317"
---
# <a name="excluding-function"></a><span data-ttu-id="99b77-102">Függvény kizárása</span><span class="sxs-lookup"><span data-stu-id="99b77-102">Excluding function</span></span>

<span data-ttu-id="99b77-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="99b77-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="99b77-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="99b77-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="99b77-105">Egy olyan tömböt ad vissza, amely egy másik tömb elemeit tartalmazza, és az indexek adott listáján szereplő elemeket is kizárja.</span><span class="sxs-lookup"><span data-stu-id="99b77-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="99b77-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="99b77-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="99b77-107">eltávolítás: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="99b77-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="99b77-108">Az indexek tömbje, amely azt jelöli, hogy mely elemeket kell kizárni a kimenetből.</span><span class="sxs-lookup"><span data-stu-id="99b77-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="99b77-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="99b77-109">array : 'T[]</span></span>

<span data-ttu-id="99b77-110">Az a tömb, amely a kimeneti tömbben szereplő értékeket veszi fel.</span><span class="sxs-lookup"><span data-stu-id="99b77-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="99b77-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="99b77-111">Output : 'T[]</span></span>

<span data-ttu-id="99b77-112">Egy olyan tömb `output` `output[0]` , amely az első eleme, `array` amelynek az indexe nem jelenik meg `remove` , például `output[1]` a második ilyen elem, és így tovább.</span><span class="sxs-lookup"><span data-stu-id="99b77-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="99b77-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="99b77-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="99b77-114">Nem</span><span class="sxs-lookup"><span data-stu-id="99b77-114">'T</span></span>

<span data-ttu-id="99b77-115">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="99b77-115">The type of the array elements.</span></span>