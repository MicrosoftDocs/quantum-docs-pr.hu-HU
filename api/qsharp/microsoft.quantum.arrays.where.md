---
uid: Microsoft.Quantum.Arrays.Where
title: Where függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 1c9fa0463ed49788d12502257d735b965565d1ab
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718756"
---
# <a name="where-function"></a><span data-ttu-id="c97bf-102">Where függvény</span><span class="sxs-lookup"><span data-stu-id="c97bf-102">Where function</span></span>

<span data-ttu-id="c97bf-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c97bf-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c97bf-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c97bf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c97bf-105">Egy predikátum és egy tömb miatt a tömb azon indexeit adja vissza, amelyekben a predikátum igaz.</span><span class="sxs-lookup"><span data-stu-id="c97bf-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="c97bf-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c97bf-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="c97bf-107">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="c97bf-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c97bf-108">Az `'T` elemek szűréséhez használt logikai értékből származó függvény.</span><span class="sxs-lookup"><span data-stu-id="c97bf-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="c97bf-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="c97bf-109">array : 'T[]</span></span>

<span data-ttu-id="c97bf-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="c97bf-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="c97bf-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c97bf-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c97bf-112">Az indexek tömbje, ahol `predicate` igaz.</span><span class="sxs-lookup"><span data-stu-id="c97bf-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c97bf-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c97bf-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c97bf-114">Nem</span><span class="sxs-lookup"><span data-stu-id="c97bf-114">'T</span></span>

<span data-ttu-id="c97bf-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="c97bf-115">The type of `array` elements.</span></span>