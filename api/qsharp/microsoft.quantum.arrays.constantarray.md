---
uid: Microsoft.Quantum.Arrays.ConstantArray
title: ConstantArray függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ConstantArray
qsharp.summary: Creates an array of given length with all elements equal to given value.
ms.openlocfilehash: 848f18944829d08a10ec602dcb5d99c100c81f76
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719416"
---
# <a name="constantarray-function"></a><span data-ttu-id="e8faa-102">ConstantArray függvény</span><span class="sxs-lookup"><span data-stu-id="e8faa-102">ConstantArray function</span></span>

<span data-ttu-id="e8faa-103">Névtér: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e8faa-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e8faa-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8faa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8faa-105">Egy adott hosszúságú tömböt hoz létre a megadott értékkel egyenlő összes elemmel.</span><span class="sxs-lookup"><span data-stu-id="e8faa-105">Creates an array of given length with all elements equal to given value.</span></span>

```qsharp
function ConstantArray<'T> (length : Int, value : 'T) : 'T[]
```


## <a name="input"></a><span data-ttu-id="e8faa-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e8faa-106">Input</span></span>

### <a name="length--int"></a><span data-ttu-id="e8faa-107">Hossz: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e8faa-107">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e8faa-108">Az új tömb hossza.</span><span class="sxs-lookup"><span data-stu-id="e8faa-108">Length of the new array.</span></span>


### <a name="value--t"></a><span data-ttu-id="e8faa-109">érték: nem</span><span class="sxs-lookup"><span data-stu-id="e8faa-109">value : 'T</span></span>

<span data-ttu-id="e8faa-110">Az új tömb egyes elemeinek értéke.</span><span class="sxs-lookup"><span data-stu-id="e8faa-110">The value of each element of the new array.</span></span>



## <a name="output--t"></a><span data-ttu-id="e8faa-111">Kimenet: 'T []</span><span class="sxs-lookup"><span data-stu-id="e8faa-111">Output : 'T[]</span></span>

<span data-ttu-id="e8faa-112">Egy új hosszúságú tömb `length` , amely minden elemnél `value` .</span><span class="sxs-lookup"><span data-stu-id="e8faa-112">A new array of length `length`, such that every element is `value`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e8faa-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="e8faa-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e8faa-114">Nem</span><span class="sxs-lookup"><span data-stu-id="e8faa-114">'T</span></span>

