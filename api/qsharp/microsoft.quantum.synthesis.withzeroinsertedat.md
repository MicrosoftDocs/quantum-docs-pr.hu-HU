---
uid: Microsoft.Quantum.Synthesis.WithZeroInsertedAt
title: WithZeroInsertedAt függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: WithZeroInsertedAt
qsharp.summary: Insert a 0-bit into an integer
ms.openlocfilehash: 7d5f8838b6ae555524fb0e82e14f93e6c77e43d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855198"
---
# <a name="withzeroinsertedat-function"></a><span data-ttu-id="e9bc4-102">WithZeroInsertedAt függvény</span><span class="sxs-lookup"><span data-stu-id="e9bc4-102">WithZeroInsertedAt function</span></span>

<span data-ttu-id="e9bc4-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="e9bc4-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="e9bc4-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e9bc4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e9bc4-105">0 bites egész szám beszúrása</span><span class="sxs-lookup"><span data-stu-id="e9bc4-105">Insert a 0-bit into an integer</span></span>

```qsharp
function WithZeroInsertedAt (position : Int, value : Int) : Int
```


## <a name="description"></a><span data-ttu-id="e9bc4-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="e9bc4-106">Description</span></span>

<span data-ttu-id="e9bc4-107">A művelet egész számot vesz igénybe, egy 0 bitet szúr be `position` , és egész számként adja vissza a frissített értéket.</span><span class="sxs-lookup"><span data-stu-id="e9bc4-107">This operation takes an integer, inserts a 0 at bit `position`, and returns the updated value as an integer.</span></span>  <span data-ttu-id="e9bc4-108">Ha például egy 0 pozíciót szúr be a 2. helyen a 10-es számú (10 $ _ {10} = 1010_ $) értékbe, {2} a a 18 értéket adja vissza (18 – 18 – 5 – 5 – 5 {10} 10010_ {2} $</span><span class="sxs-lookup"><span data-stu-id="e9bc4-108">For example, inserting a 0 at position 2 in the number 10 ($10_{10} = 1010_{2}$) returns the number 18 ($18_{10} = 10010_{2}$).</span></span>

## <a name="input"></a><span data-ttu-id="e9bc4-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e9bc4-109">Input</span></span>

### <a name="position--int"></a><span data-ttu-id="e9bc4-110">pozíció: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e9bc4-110">position : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e9bc4-111">Az a pozíció, amelybe a 0 beszúrt</span><span class="sxs-lookup"><span data-stu-id="e9bc4-111">The position at which 0 is inserted</span></span>


### <a name="value--int"></a><span data-ttu-id="e9bc4-112">érték: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e9bc4-112">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e9bc4-113">A módosított érték</span><span class="sxs-lookup"><span data-stu-id="e9bc4-113">The value that is modified</span></span>



## <a name="output--int"></a><span data-ttu-id="e9bc4-114">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e9bc4-114">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e9bc4-115">Módosított érték</span><span class="sxs-lookup"><span data-stu-id="e9bc4-115">Modified value</span></span>