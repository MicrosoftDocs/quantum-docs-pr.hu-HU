---
uid: Microsoft.Quantum.Arrays.ElementsAt
title: ElementsAt függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementsAt
qsharp.summary: Returns the array's elements at a given range of indices.
ms.openlocfilehash: b4bbba4dc83c4f9b89cdcb8ec32769f1c586357e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719344"
---
# <a name="elementsat-function"></a><span data-ttu-id="e8940-102">ElementsAt függvény</span><span class="sxs-lookup"><span data-stu-id="e8940-102">ElementsAt function</span></span>

<span data-ttu-id="e8940-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e8940-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e8940-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8940-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8940-105">A tömb azon elemeit adja vissza, amelyek az indexek adott tartományában vannak.</span><span class="sxs-lookup"><span data-stu-id="e8940-105">Returns the array's elements at a given range of indices.</span></span>

```qsharp
function ElementsAt<'T> (range : Range, array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e8940-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e8940-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="e8940-107">tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="e8940-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="e8940-108">Array indexek tartománya</span><span class="sxs-lookup"><span data-stu-id="e8940-108">Range of array indexes</span></span>


### <a name="array--t"></a><span data-ttu-id="e8940-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="e8940-109">array : 'T[]</span></span>

<span data-ttu-id="e8940-110">Tömb</span><span class="sxs-lookup"><span data-stu-id="e8940-110">Array</span></span>



## <a name="output--t"></a><span data-ttu-id="e8940-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="e8940-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="e8940-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e8940-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e8940-113">Nem</span><span class="sxs-lookup"><span data-stu-id="e8940-113">'T</span></span>

<span data-ttu-id="e8940-114">Az egyes elemeinek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="e8940-114">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e8940-115">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e8940-115">See Also</span></span>

- [<span data-ttu-id="e8940-116">Microsoft. Quantum. Arrays. ElementAt</span><span class="sxs-lookup"><span data-stu-id="e8940-116">Microsoft.Quantum.Arrays.ElementAt</span></span>](xref:Microsoft.Quantum.Arrays.ElementAt)
- [<span data-ttu-id="e8940-117">Microsoft. Quantum. Arrays. LookupFunction</span><span class="sxs-lookup"><span data-stu-id="e8940-117">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)