---
uid: Microsoft.Quantum.Arrays.Padded
title: Párnázott függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 556e5f5175ee54470a99f32c037eeb2cd80588d0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845562"
---
# <a name="padded-function"></a><span data-ttu-id="1b2a3-102">Párnázott függvény</span><span class="sxs-lookup"><span data-stu-id="1b2a3-102">Padded function</span></span>

<span data-ttu-id="1b2a3-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1b2a3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1b2a3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b2a3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1b2a3-105">Egy olyan tömböt ad vissza, amely a megadott értékekkel megadott hosszúságú.</span><span class="sxs-lookup"><span data-stu-id="1b2a3-105">Returns an array padded at with specified values up to a specified length.</span></span>

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="1b2a3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1b2a3-106">Input</span></span>

### <a name="nelementstotal--int"></a><span data-ttu-id="1b2a3-107">nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1b2a3-107">nElementsTotal : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1b2a3-108">A párnázott tömb hossza.</span><span class="sxs-lookup"><span data-stu-id="1b2a3-108">The length of the padded array.</span></span> <span data-ttu-id="1b2a3-109">Ha ez pozitív, `inputArray` akkor a rendszer a fej tetején található.</span><span class="sxs-lookup"><span data-stu-id="1b2a3-109">If this is positive, `inputArray` is padded at the head.</span></span> <span data-ttu-id="1b2a3-110">Ha ez negatív, `inputArray` a rendszer a farok margóján található.</span><span class="sxs-lookup"><span data-stu-id="1b2a3-110">If this is negative, `inputArray` is padded at the tail.</span></span>


### <a name="defaultelement--t"></a><span data-ttu-id="1b2a3-111">defaultElement: nem</span><span class="sxs-lookup"><span data-stu-id="1b2a3-111">defaultElement : 'T</span></span>

<span data-ttu-id="1b2a3-112">A kitöltési elemekhez használandó alapértelmezett érték.</span><span class="sxs-lookup"><span data-stu-id="1b2a3-112">Default value to use for padding elements.</span></span>


### <a name="inputarray--t"></a><span data-ttu-id="1b2a3-113">inputArray: nem []</span><span class="sxs-lookup"><span data-stu-id="1b2a3-113">inputArray : 'T[]</span></span>

<span data-ttu-id="1b2a3-114">Az a tömb, amelynek értékei a kimeneti tömb élén vannak.</span><span class="sxs-lookup"><span data-stu-id="1b2a3-114">Array whose values are at the head of the output array.</span></span>



## <a name="output--t"></a><span data-ttu-id="1b2a3-115">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="1b2a3-115">Output : 'T[]</span></span>

<span data-ttu-id="1b2a3-116">Egy tömb `output` , amely a `inputArray` fej és a `defaultElement` `output` Hossz közötti távolságú `nElementsTotal`</span><span class="sxs-lookup"><span data-stu-id="1b2a3-116">An array `output` that is the `inputArray` padded at the head with `defaultElement`s until `output` has length `nElementsTotal`</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1b2a3-117">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="1b2a3-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1b2a3-118">Nem</span><span class="sxs-lookup"><span data-stu-id="1b2a3-118">'T</span></span>

<span data-ttu-id="1b2a3-119">A tömb elemeinek típusa</span><span class="sxs-lookup"><span data-stu-id="1b2a3-119">The type of the array elements.</span></span>

## <a name="example"></a><span data-ttu-id="1b2a3-120">Példa</span><span class="sxs-lookup"><span data-stu-id="1b2a3-120">Example</span></span>

```qsharp
let array = [10, 11, 12];
// The following line returns [10, 12, 15, 2, 2, 2].
let output = Padded(-6, array, 2);
// The following line returns [2, 2, 2, 10, 12, 15].
let output = Padded(6, array, 2);
```