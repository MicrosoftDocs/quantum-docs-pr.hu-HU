---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 414b703151b9152aa69709d9c28e68e5ae63506f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228865"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="abc79-102">WithZeroInsertedAt függvény</span><span class="sxs-lookup"><span data-stu-id="abc79-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="abc79-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="abc79-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="abc79-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="abc79-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="abc79-105">0 bites egész szám beszúrása</span><span class="sxs-lookup"><span data-stu-id="abc79-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="abc79-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="abc79-106">Description</span></span>

<span data-ttu-id="abc79-107">A művelet egész számot vesz igénybe, egy 0 bitet szúr be `position` , és egész számként adja vissza a frissített értéket.</span><span class="sxs-lookup"><span data-stu-id="abc79-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="abc79-108">Ha például egy 0 pozíciót szúr be a 2. helyen a 10-es számú (10 $ _ {10} = 1010_ $) értékbe, {2} a a 18 értéket adja vissza (18 – 18 – 5 – 5 – 5 {10} 10010_ {2} $</span><span class="sxs-lookup"><span data-stu-id="abc79-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="abc79-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="abc79-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="abc79-110">pozíció: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="abc79-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="abc79-111">Az a pozíció, amelybe a 0 beszúrt</span><span class="sxs-lookup"><span data-stu-id="abc79-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="abc79-112">érték: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="abc79-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="abc79-113">A módosított érték</span><span class="sxs-lookup"><span data-stu-id="abc79-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="abc79-114">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="abc79-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="abc79-115">Módosított érték</span><span class="sxs-lookup"><span data-stu-id="abc79-115">Modified value</span></span>