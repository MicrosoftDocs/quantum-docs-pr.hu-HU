---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 8d69aa119c25a0f64743fec36c00ecdef2450c44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855317"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="2abd7-102">SizeAdjustedTruthTable függvény</span><span class="sxs-lookup"><span data-stu-id="2abd7-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="2abd7-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="2abd7-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="2abd7-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2abd7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2abd7-105">Az igazság táblázatának beállítása logikai értékek tömbje alapján a változók száma szerint</span><span class="sxs-lookup"><span data-stu-id="2abd7-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="2abd7-106">A rendszer egy új tömböt ad vissza `2^numVars` , ami valószínűleg azt igényli, hogy a méretet kibővítse `table` a `false` bejegyzésekkel, vagy csonkolja azokat az `2^numVars` elemekre.</span><span class="sxs-lookup"><span data-stu-id="2abd7-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="2abd7-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2abd7-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="2abd7-108">tábla: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="2abd7-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="2abd7-109">Igazság tábla az igazság értékek tömbje</span><span class="sxs-lookup"><span data-stu-id="2abd7-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="2abd7-110">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2abd7-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2abd7-111">Változók száma</span><span class="sxs-lookup"><span data-stu-id="2abd7-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="2abd7-112">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="2abd7-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="2abd7-113">Méretre igazított igazság táblázat</span><span class="sxs-lookup"><span data-stu-id="2abd7-113">Size adjusted truth table</span></span>