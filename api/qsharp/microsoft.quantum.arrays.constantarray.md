---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 8cba68af2f1e178a1ef96921283f85e4feb498ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210063"
---
# <a name="constantarray-function"></a><span data-ttu-id="514e5-102">ConstantArray függvény</span><span class="sxs-lookup"><span data-stu-id="514e5-102">ConstantArray function</span></span>

<span data-ttu-id="514e5-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="514e5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="514e5-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="514e5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="514e5-105">Egy adott hosszúságú tömböt hoz létre a megadott értékkel egyenlő összes elemmel.</span><span class="sxs-lookup"><span data-stu-id="514e5-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="514e5-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="514e5-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="514e5-107">Hossz: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="514e5-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="514e5-108">Az új tömb hossza.</span><span class="sxs-lookup"><span data-stu-id="514e5-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="514e5-109">érték: nem</span><span class="sxs-lookup"><span data-stu-id="514e5-109">value : 'T</span></span>

<span data-ttu-id="514e5-110">Az új tömb egyes elemeinek értéke.</span><span class="sxs-lookup"><span data-stu-id="514e5-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="514e5-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="514e5-111">Output : 'T[]</span></span>

<span data-ttu-id="514e5-112">Egy új hosszúságú tömb `length` , amely minden elemnél `value` .</span><span class="sxs-lookup"><span data-stu-id="514e5-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="514e5-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="514e5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="514e5-114">Nem</span><span class="sxs-lookup"><span data-stu-id="514e5-114">'T</span></span>

