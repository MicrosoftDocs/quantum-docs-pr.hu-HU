---
uid: Microsoft.Quantum.Arrays.Exclude
title: Funkció kizárása
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: e1fa7e728d4846db90872055454a8182a77a518b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719284"
---
# <a name="exclude-function"></a><span data-ttu-id="5bbd8-102">Funkció kizárása</span><span class="sxs-lookup"><span data-stu-id="5bbd8-102">Exclude function</span></span>

<span data-ttu-id="5bbd8-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5bbd8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5bbd8-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5bbd8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5bbd8-105">Egy olyan tömböt ad vissza, amely egy másik tömb elemeit tartalmazza, és az indexek adott listáján szereplő elemeket is kizárja.</span><span class="sxs-lookup"><span data-stu-id="5bbd8-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="5bbd8-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5bbd8-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="5bbd8-107">eltávolítás: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="5bbd8-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="5bbd8-108">Az indexek tömbje, amely azt jelöli, hogy mely elemeket kell kizárni a kimenetből.</span><span class="sxs-lookup"><span data-stu-id="5bbd8-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="5bbd8-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="5bbd8-109">array : 'T[]</span></span>

<span data-ttu-id="5bbd8-110">Az a tömb, amely a kimeneti tömbben szereplő értékeket veszi fel.</span><span class="sxs-lookup"><span data-stu-id="5bbd8-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="5bbd8-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="5bbd8-111">Output : 'T[]</span></span>

<span data-ttu-id="5bbd8-112">Egy olyan tömb `output` `output[0]` , amely az első eleme, `array` amelynek az indexe nem jelenik meg `remove` , például `output[1]` a második ilyen elem, és így tovább.</span><span class="sxs-lookup"><span data-stu-id="5bbd8-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5bbd8-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="5bbd8-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5bbd8-114">Nem</span><span class="sxs-lookup"><span data-stu-id="5bbd8-114">'T</span></span>

<span data-ttu-id="5bbd8-115">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="5bbd8-115">The type of the array elements.</span></span>