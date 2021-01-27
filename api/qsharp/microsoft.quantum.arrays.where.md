---
uid: Microsoft.Quantum.Arrays.Where
title: Where függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 4a938114689177f7a9ee182e6e5f36debe4edac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842218"
---
# <a name="where-function"></a><span data-ttu-id="79e93-102">Where függvény</span><span class="sxs-lookup"><span data-stu-id="79e93-102">Where function</span></span>

<span data-ttu-id="79e93-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="79e93-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="79e93-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="79e93-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="79e93-105">Egy predikátum és egy tömb miatt a tömb azon indexeit adja vissza, amelyekben a predikátum igaz.</span><span class="sxs-lookup"><span data-stu-id="79e93-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="79e93-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="79e93-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="79e93-107">predikátum: nem > [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="79e93-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="79e93-108">Az `'T` elemek szűréséhez használt logikai értékből származó függvény.</span><span class="sxs-lookup"><span data-stu-id="79e93-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="79e93-109">tömb: 'T []</span><span class="sxs-lookup"><span data-stu-id="79e93-109">array : 'T[]</span></span>

<span data-ttu-id="79e93-110">Elemek tömbje `'T` .</span><span class="sxs-lookup"><span data-stu-id="79e93-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="79e93-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="79e93-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="79e93-112">Az indexek tömbje, ahol `predicate` igaz.</span><span class="sxs-lookup"><span data-stu-id="79e93-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="79e93-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="79e93-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="79e93-114">Nem</span><span class="sxs-lookup"><span data-stu-id="79e93-114">'T</span></span>

<span data-ttu-id="79e93-115">Az elemek típusa `array` .</span><span class="sxs-lookup"><span data-stu-id="79e93-115">The type of `array` elements.</span></span>