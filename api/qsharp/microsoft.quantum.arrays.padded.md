---
uid: Microsoft.Quantum.Arrays.Padded
title: Párnázott függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 2b7a80d1cf5c82a1ff52bc4aa207cfe335b40061
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220535"
---
# <a name="padded-function"></a><span data-ttu-id="2366b-102">Párnázott függvény</span><span class="sxs-lookup"><span data-stu-id="2366b-102">Padded function</span></span>

<span data-ttu-id="2366b-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2366b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2366b-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2366b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2366b-105">Egy olyan tömböt ad vissza, amely a megadott értékekkel megadott hosszúságú.</span><span class="sxs-lookup"><span data-stu-id="2366b-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="2366b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2366b-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="2366b-107">nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2366b-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2366b-108">A párnázott tömb hossza.</span><span class="sxs-lookup"><span data-stu-id="2366b-108">The length of the padded array.</span></span> <span data-ttu-id="2366b-109">Ha ez pozitív, `inputArray` akkor a rendszer a fej tetején található.</span><span class="sxs-lookup"><span data-stu-id="2366b-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="2366b-110">Ha ez negatív, `inputArray` a rendszer a farok margóján található.</span><span class="sxs-lookup"><span data-stu-id="2366b-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="2366b-111">defaultElement: nem</span><span class="sxs-lookup"><span data-stu-id="2366b-111">defaultElement : 'T</span></span>

<span data-ttu-id="2366b-112">A kitöltési elemekhez használandó alapértelmezett érték.</span><span class="sxs-lookup"><span data-stu-id="2366b-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="2366b-113">inputArray: nem []</span><span class="sxs-lookup"><span data-stu-id="2366b-113">inputArray : 'T[]</span></span>

<span data-ttu-id="2366b-114">Az a tömb, amelynek értékei a kimeneti tömb élén vannak.</span><span class="sxs-lookup"><span data-stu-id="2366b-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="2366b-115">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="2366b-115">Output : 'T[]</span></span>

<span data-ttu-id="2366b-116">Egy tömb `output` , amely a `inputArray` fej és a `defaultElement` `output` Hossz közötti távolságú `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="2366b-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2366b-117">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2366b-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2366b-118">Nem</span><span class="sxs-lookup"><span data-stu-id="2366b-118">'T</span></span>

<span data-ttu-id="2366b-119">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="2366b-119">The type of the array elements.</span></span>