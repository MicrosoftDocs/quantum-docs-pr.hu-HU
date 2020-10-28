---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows-függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718745"
---
# <a name="windows-function"></a><span data-ttu-id="9c637-102">Windows-függvény</span><span class="sxs-lookup"><span data-stu-id="9c637-102">Windows function</span></span>

<span data-ttu-id="9c637-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9c637-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9c637-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9c637-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9c637-105">Az összes egymást követő altömbet adja vissza `size` .</span><span class="sxs-lookup"><span data-stu-id="9c637-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="9c637-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="9c637-106">Description</span></span>

<span data-ttu-id="9c637-107">Ez a függvény az összes olyan `n - size + 1` altömbt adja vissza `size` sorrendben, ahol a hossz a következő: `n` `arr` .</span><span class="sxs-lookup"><span data-stu-id="9c637-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="9c637-108">Az első altömb az utolsó altömbig tart `arr[0..size - 1], arr[1..size], arr[2..size + 1]` `arr[n - size..n - 1]` .</span><span class="sxs-lookup"><span data-stu-id="9c637-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="9c637-109">Ha `size <= 0` vagy `size > n` , üres tömböt ad vissza.</span><span class="sxs-lookup"><span data-stu-id="9c637-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="9c637-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9c637-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="9c637-111">Méret: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9c637-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9c637-112">Az altömbök hossza.</span><span class="sxs-lookup"><span data-stu-id="9c637-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="9c637-113">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="9c637-113">array : 'T[]</span></span>

<span data-ttu-id="9c637-114">Elemek tömbje.</span><span class="sxs-lookup"><span data-stu-id="9c637-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="9c637-115">Kimenet: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="9c637-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9c637-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="9c637-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9c637-117">Nem</span><span class="sxs-lookup"><span data-stu-id="9c637-117">'T</span></span>

<span data-ttu-id="9c637-118">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="9c637-118">The type of `array` elements.</span></span>