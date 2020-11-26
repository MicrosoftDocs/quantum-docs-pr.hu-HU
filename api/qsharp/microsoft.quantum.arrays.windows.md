---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows-függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 8f32a23aa4379744b84c3b8d9c8f565e61c3c64e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219889"
---
# <a name="windows-function"></a><span data-ttu-id="b86bb-102">Windows-függvény</span><span class="sxs-lookup"><span data-stu-id="b86bb-102">Windows function</span></span>

<span data-ttu-id="b86bb-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b86bb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b86bb-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b86bb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b86bb-105">Az összes egymást követő altömbet adja vissza `size` .</span><span class="sxs-lookup"><span data-stu-id="b86bb-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="b86bb-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="b86bb-106">Description</span></span>

<span data-ttu-id="b86bb-107">Ez a függvény az összes olyan `n - size + 1` altömbt adja vissza `size` sorrendben, ahol a hossz a következő: `n` `arr` .</span><span class="sxs-lookup"><span data-stu-id="b86bb-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="b86bb-108">Az első altömb az utolsó altömbig tart `arr[0..size - 1], arr[1..size], arr[2..size + 1]` `arr[n - size..n - 1]` .</span><span class="sxs-lookup"><span data-stu-id="b86bb-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="b86bb-109">Ha `size <= 0` vagy `size > n` , üres tömböt ad vissza.</span><span class="sxs-lookup"><span data-stu-id="b86bb-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="b86bb-110">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b86bb-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="b86bb-111">Méret: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b86bb-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b86bb-112">Az altömbök hossza.</span><span class="sxs-lookup"><span data-stu-id="b86bb-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="b86bb-113">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="b86bb-113">array : 'T[]</span></span>

<span data-ttu-id="b86bb-114">Elemek tömbje.</span><span class="sxs-lookup"><span data-stu-id="b86bb-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="b86bb-115">Kimenet: 'T [] []</span><span class="sxs-lookup"><span data-stu-id="b86bb-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b86bb-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="b86bb-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b86bb-117">Nem</span><span class="sxs-lookup"><span data-stu-id="b86bb-117">'T</span></span>

<span data-ttu-id="b86bb-118">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="b86bb-118">The type of `array` elements.</span></span>