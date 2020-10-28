---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713361"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="0e85c-102">RangeAsIntArray függvény</span><span class="sxs-lookup"><span data-stu-id="0e85c-102">RangeAsIntArray function</span></span>

<span data-ttu-id="0e85c-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="0e85c-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="0e85c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0e85c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0e85c-105">A (Start) számú egész számok tömbjét hozza létre `arr` . lépés.. végén.</span><span class="sxs-lookup"><span data-stu-id="0e85c-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="0e85c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0e85c-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="0e85c-107">tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="0e85c-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="0e85c-108">Egy `Range` `start..step..end` tömbre konvertálandó érték.</span><span class="sxs-lookup"><span data-stu-id="0e85c-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="0e85c-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0e85c-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0e85c-110">Az egész számok új tömbje, amely a által megismétlik által megismételt értékeknek felel meg `range` .</span><span class="sxs-lookup"><span data-stu-id="0e85c-110">A new array of integers corresponding to values iterated over by `range`.</span></span>