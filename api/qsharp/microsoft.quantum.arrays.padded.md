---
uid: Microsoft.Quantum.Arrays.Padded
title: Párnázott függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 8742d4726e7ee32349bf3d0bd5077352ffca350b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718984"
---
# <a name="padded-function"></a><span data-ttu-id="75c0c-102">Párnázott függvény</span><span class="sxs-lookup"><span data-stu-id="75c0c-102">Padded function</span></span>

<span data-ttu-id="75c0c-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="75c0c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="75c0c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="75c0c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="75c0c-105">Egy olyan tömböt ad vissza, amely a megadott értékekkel megadott hosszúságú.</span><span class="sxs-lookup"><span data-stu-id="75c0c-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="75c0c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="75c0c-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="75c0c-107">nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="75c0c-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="75c0c-108">A párnázott tömb hossza.</span><span class="sxs-lookup"><span data-stu-id="75c0c-108">The length of the padded array.</span></span> <span data-ttu-id="75c0c-109">Ha ez pozitív, `inputArray` akkor a rendszer a fej tetején található.</span><span class="sxs-lookup"><span data-stu-id="75c0c-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="75c0c-110">Ha ez negatív, `inputArray` a rendszer a farok margóján található.</span><span class="sxs-lookup"><span data-stu-id="75c0c-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="75c0c-111">defaultElement: nem</span><span class="sxs-lookup"><span data-stu-id="75c0c-111">defaultElement : 'T</span></span>

<span data-ttu-id="75c0c-112">A kitöltési elemekhez használandó alapértelmezett érték.</span><span class="sxs-lookup"><span data-stu-id="75c0c-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="75c0c-113">inputArray: nem []</span><span class="sxs-lookup"><span data-stu-id="75c0c-113">inputArray : 'T[]</span></span>

<span data-ttu-id="75c0c-114">Az a tömb, amelynek értékei a kimeneti tömb élén vannak.</span><span class="sxs-lookup"><span data-stu-id="75c0c-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="75c0c-115">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="75c0c-115">Output : 'T[]</span></span>

<span data-ttu-id="75c0c-116">Egy tömb `output` , amely a `inputArray` fej és a `defaultElement` `output` Hossz közötti távolságú `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="75c0c-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="75c0c-117">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="75c0c-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="75c0c-118">Nem</span><span class="sxs-lookup"><span data-stu-id="75c0c-118">'T</span></span>

<span data-ttu-id="75c0c-119">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="75c0c-119">The type of the array elements.</span></span>