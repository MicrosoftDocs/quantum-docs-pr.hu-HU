---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833303"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="7d262-102">IntAsBoolArray függvény</span><span class="sxs-lookup"><span data-stu-id="7d262-102">IntAsBoolArray function</span></span>

<span data-ttu-id="7d262-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="7d262-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="7d262-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d262-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d262-105">Egy nem negatív egész szám bináris ábrázolását állítja elő a visszaadott tömb kis endian ábrázolásával.</span><span class="sxs-lookup"><span data-stu-id="7d262-105">Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="7d262-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7d262-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="7d262-107">szám: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7d262-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7d262-108">Egy nem negatív egész szám, amely logikai értékek tömbje számára lesz konvertálva.</span><span class="sxs-lookup"><span data-stu-id="7d262-108">A non-negative integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="7d262-109">BITS: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7d262-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7d262-110">A bináris ábrázolásban lévő bitek száma `number` .</span><span class="sxs-lookup"><span data-stu-id="7d262-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7d262-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="7d262-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="7d262-112">A logikai értékek tömbje, amely a értéket jelképezi `number` .</span><span class="sxs-lookup"><span data-stu-id="7d262-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7d262-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="7d262-113">Remarks</span></span>

<span data-ttu-id="7d262-114">A bemenetnek `bits` 0 és 63 közöttinek kell lennie.</span><span class="sxs-lookup"><span data-stu-id="7d262-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="7d262-115">A bemenetnek `number` 0 és $2 ^ {\texttt{BITS}}-$1 között kell lennie.</span><span class="sxs-lookup"><span data-stu-id="7d262-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>