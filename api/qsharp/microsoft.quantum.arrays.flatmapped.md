---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: 3e75c7703471a2986812df660c2f9328f1536d22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719249"
---
# <a name="flatmapped-function"></a><span data-ttu-id="156a8-102">FlatMapped függvény</span><span class="sxs-lookup"><span data-stu-id="156a8-102">FlatMapped function</span></span>

<span data-ttu-id="156a8-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="156a8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="156a8-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="156a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="156a8-105">Egy tömb és egy függvény, amely egy tömb elemet képez egy kimeneti tömbhöz, visszaadja az összefűzött kimeneti tömböket minden egyes tömb elemhez.</span><span class="sxs-lookup"><span data-stu-id="156a8-105">Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.</span></span>

```qsharp
function FlatMapped<'TInput, 'TOutput> (mapper : ('TInput -> 'TOutput[]), array : 'TInput[]) : 'TOutput[]
```


## <a name="input"></a><span data-ttu-id="156a8-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="156a8-106">Input</span></span>

### <a name="mapper--tinput---toutput"></a><span data-ttu-id="156a8-107">Mapper: ' TInput-> ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="156a8-107">mapper : 'TInput -> 'TOutput[]</span></span>

<span data-ttu-id="156a8-108">A-ből származó függvény, `'TInput` `'TOutput[]` amely a tömb elemeinek hozzárendelésére szolgál.</span><span class="sxs-lookup"><span data-stu-id="156a8-108">A function from `'TInput` to `'TOutput[]` that is used to map array elements.</span></span>


### <a name="array--tinput"></a><span data-ttu-id="156a8-109">tömb: "TInput []</span><span class="sxs-lookup"><span data-stu-id="156a8-109">array : 'TInput[]</span></span>

<span data-ttu-id="156a8-110">Elemek tömbje.</span><span class="sxs-lookup"><span data-stu-id="156a8-110">An array of elements.</span></span>



## <a name="output--toutput"></a><span data-ttu-id="156a8-111">Kimenet: ' TOutput []</span><span class="sxs-lookup"><span data-stu-id="156a8-111">Output : 'TOutput[]</span></span>

<span data-ttu-id="156a8-112">Egy tömb, `'TOutput[]` amely a leképezési függvény által generált összes tömb összefűzése.</span><span class="sxs-lookup"><span data-stu-id="156a8-112">An array of `'TOutput[]` which is the concatenation of all arrays generated by the mapping function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="156a8-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="156a8-113">Type Parameters</span></span>

### <a name="tinput"></a><span data-ttu-id="156a8-114">'TInput</span><span class="sxs-lookup"><span data-stu-id="156a8-114">'TInput</span></span>

<span data-ttu-id="156a8-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="156a8-115">The type of `array` elements.</span></span>
### <a name="toutput"></a><span data-ttu-id="156a8-116">'TOutput</span><span class="sxs-lookup"><span data-stu-id="156a8-116">'TOutput</span></span>

<span data-ttu-id="156a8-117">A `mapper` függvény az ilyen típusú tömböket adja vissza.</span><span class="sxs-lookup"><span data-stu-id="156a8-117">The `mapper` function returns arrays of this type.</span></span>