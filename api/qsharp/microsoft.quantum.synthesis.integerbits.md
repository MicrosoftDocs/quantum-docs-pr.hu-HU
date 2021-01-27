---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: 3352c1b3003ee387fb03b72461fedb400e29046d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855401"
---
# <a name="integerbits-function"></a><span data-ttu-id="281d7-102">IntegerBits függvény</span><span class="sxs-lookup"><span data-stu-id="281d7-102">IntegerBits function</span></span>

<span data-ttu-id="281d7-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="281d7-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="281d7-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="281d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="281d7-105">Az összes olyan pozíciót adja vissza, amelyben egy egész számú bit be van állítva.</span><span class="sxs-lookup"><span data-stu-id="281d7-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="281d7-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="281d7-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="281d7-107">érték: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="281d7-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="281d7-108">Nem negatív szám.</span><span class="sxs-lookup"><span data-stu-id="281d7-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="281d7-109">Hossz: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="281d7-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="281d7-110">A bináris kiterjesztésű bitek száma `value` .</span><span class="sxs-lookup"><span data-stu-id="281d7-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="281d7-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="281d7-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="281d7-112">Az összes bitet tartalmazó tömb (0-tól kezdődően), amely a bináris kiterjesztésben 1 az `value` összes bit pozícióig `length - 1` .</span><span class="sxs-lookup"><span data-stu-id="281d7-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="281d7-113">A tömbben az összes pozíciót növekvő sorrendben rendezi a rendszer.</span><span class="sxs-lookup"><span data-stu-id="281d7-113">All positions are ordered in the array by position in an increasing order.</span></span>

## <a name="example"></a><span data-ttu-id="281d7-114">Példa</span><span class="sxs-lookup"><span data-stu-id="281d7-114">Example</span></span>

```qsharp
IntegerBits(23, 5); // [0, 1, 2, 4]
IntegerBits(10, 4); // [1, 3]
```