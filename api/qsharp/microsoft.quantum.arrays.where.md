---
uid: Microsoft.Quantum.Arrays.Where
title: Where függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 97598aa25d2d085aaab94f3d60ee64db9e2b89d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219923"
---
# <a name="where-function"></a><span data-ttu-id="841d4-102">Where függvény</span><span class="sxs-lookup"><span data-stu-id="841d4-102">Where function</span></span>

<span data-ttu-id="841d4-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="841d4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="841d4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="841d4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="841d4-105">Egy predikátum és egy tömb miatt a tömb azon indexeit adja vissza, amelyekben a predikátum igaz.</span><span class="sxs-lookup"><span data-stu-id="841d4-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="841d4-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="841d4-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="841d4-107">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="841d4-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="841d4-108">Az `'T` elemek szűréséhez használt logikai értékből származó függvény.</span><span class="sxs-lookup"><span data-stu-id="841d4-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="841d4-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="841d4-109">array : 'T[]</span></span>

<span data-ttu-id="841d4-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="841d4-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="841d4-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="841d4-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="841d4-112">Az indexek tömbje, ahol `predicate` igaz.</span><span class="sxs-lookup"><span data-stu-id="841d4-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="841d4-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="841d4-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="841d4-114">Nem</span><span class="sxs-lookup"><span data-stu-id="841d4-114">'T</span></span>

<span data-ttu-id="841d4-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="841d4-115">The type of `array` elements.</span></span>