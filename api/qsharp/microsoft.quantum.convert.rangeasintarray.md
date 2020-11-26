---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: f756e42aef7dc600e1fc6943a02513ac791f2320
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214007"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="f08cb-102">RangeAsIntArray függvény</span><span class="sxs-lookup"><span data-stu-id="f08cb-102">RangeAsIntArray function</span></span>

<span data-ttu-id="f08cb-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="f08cb-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="f08cb-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f08cb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f08cb-105">A (Start) számú egész számok tömbjét hozza létre `arr` . lépés.. végén.</span><span class="sxs-lookup"><span data-stu-id="f08cb-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="f08cb-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f08cb-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="f08cb-107">tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="f08cb-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="f08cb-108">Egy `Range` `start..step..end` tömbre konvertálandó érték.</span><span class="sxs-lookup"><span data-stu-id="f08cb-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="f08cb-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="f08cb-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="f08cb-110">Az egész számok új tömbje, amely a által megismétlik által megismételt értékeknek felel meg `range` .</span><span class="sxs-lookup"><span data-stu-id="f08cb-110">A new array of integers corresponding to values iterated over by `range`.</span></span>