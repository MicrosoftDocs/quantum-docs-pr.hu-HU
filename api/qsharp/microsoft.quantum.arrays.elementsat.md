---
uid: Microsoft.Quantum.Arrays.ElementsAt
title: ElementsAt függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementsAt
qsharp.summary: Returns the array's elements at a given range of indices.
ms.openlocfilehash: 83b5e97085234e8249869f858400cba265d13058
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221453"
---
# <a name="elementsat-function"></a><span data-ttu-id="0e245-102">ElementsAt függvény</span><span class="sxs-lookup"><span data-stu-id="0e245-102">ElementsAt function</span></span>

<span data-ttu-id="0e245-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0e245-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0e245-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0e245-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0e245-105">A tömb azon elemeit adja vissza, amelyek az indexek adott tartományában vannak.</span><span class="sxs-lookup"><span data-stu-id="0e245-105">Returns the array's elements at a given range of indices.</span></span>

```qsharp
function ElementsAt<'T> (range : Range, array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="0e245-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0e245-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="0e245-107">tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="0e245-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="0e245-108">Array indexek tartománya</span><span class="sxs-lookup"><span data-stu-id="0e245-108">Range of array indexes</span></span>


### <a name="array--t"></a><span data-ttu-id="0e245-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="0e245-109">array : 'T[]</span></span>

<span data-ttu-id="0e245-110">Tömb</span><span class="sxs-lookup"><span data-stu-id="0e245-110">Array</span></span>



## <a name="output--t"></a><span data-ttu-id="0e245-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="0e245-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0e245-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="0e245-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0e245-113">Nem</span><span class="sxs-lookup"><span data-stu-id="0e245-113">'T</span></span>

<span data-ttu-id="0e245-114">Az egyes elemeinek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="0e245-114">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e245-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="0e245-115">See Also</span></span>

- [<span data-ttu-id="0e245-116">Microsoft. Quantum. Arrays. ElementAt</span><span class="sxs-lookup"><span data-stu-id="0e245-116">Microsoft.Quantum.Arrays.ElementAt</span></span>](xref:Microsoft.Quantum.Arrays.ElementAt)
- [<span data-ttu-id="0e245-117">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="0e245-117">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)