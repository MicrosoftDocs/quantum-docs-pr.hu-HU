---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 3480f022df7a289594b003f201d16d8bf7c29d7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725474"
---
# <a name="sizeadjustedtruthtable-function"></a><span data-ttu-id="97468-102">SizeAdjustedTruthTable függvény</span><span class="sxs-lookup"><span data-stu-id="97468-102">SizeAdjustedTruthTable function</span></span>

<span data-ttu-id="97468-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="97468-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="97468-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="97468-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="97468-105">Az igazság táblázatának beállítása logikai értékek tömbje alapján a változók száma szerint</span><span class="sxs-lookup"><span data-stu-id="97468-105">Adjusts truth table from array of Booleans according to number of variables</span></span>

<span data-ttu-id="97468-106">A rendszer egy új tömböt ad vissza `2^numVars` , ami valószínűleg azt igényli, hogy a méretet kibővítse `table` a `false` bejegyzésekkel, vagy csonkolja azokat az `2^numVars` elemekre.</span><span class="sxs-lookup"><span data-stu-id="97468-106">A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.</span></span>

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="97468-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="97468-107">Input</span></span>

### <a name="table--bool"></a><span data-ttu-id="97468-108">tábla: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="97468-108">table : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="97468-109">Igazság tábla az igazság értékek tömbje</span><span class="sxs-lookup"><span data-stu-id="97468-109">Truth table as array of truth values</span></span>


### <a name="numvars--int"></a><span data-ttu-id="97468-110">numVars: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="97468-110">numVars : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="97468-111">Változók száma</span><span class="sxs-lookup"><span data-stu-id="97468-111">Number of variables</span></span>



## <a name="output--bool"></a><span data-ttu-id="97468-112">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="97468-112">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="97468-113">Méretre igazított igazság táblázat</span><span class="sxs-lookup"><span data-stu-id="97468-113">Size adjusted truth table</span></span>