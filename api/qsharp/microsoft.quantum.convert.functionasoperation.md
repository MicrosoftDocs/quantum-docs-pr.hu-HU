---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 90e9f0c922a77fbb6d6faf8945d4f5d1c8ff33b7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713514"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="ada7d-102">FunctionAsOperation függvény</span><span class="sxs-lookup"><span data-stu-id="ada7d-102">FunctionAsOperation function</span></span>

<span data-ttu-id="ada7d-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="ada7d-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="ada7d-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ada7d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ada7d-105">Átalakítja a függvényeket a műveletekre.</span><span class="sxs-lookup"><span data-stu-id="ada7d-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="ada7d-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="ada7d-106">Description</span></span>

<span data-ttu-id="ada7d-107">A függvény adott funkciója olyan műveletet ad vissza, amely meghívja a függvényt, és amely nem más.</span><span class="sxs-lookup"><span data-stu-id="ada7d-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="ada7d-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ada7d-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="ada7d-109">FN: "input->" kimenet</span><span class="sxs-lookup"><span data-stu-id="ada7d-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="ada7d-110">Egy műveletre konvertálandó függvény.</span><span class="sxs-lookup"><span data-stu-id="ada7d-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="ada7d-111">Kimenet: "input =>" kimenet</span><span class="sxs-lookup"><span data-stu-id="ada7d-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="ada7d-112">Olyan művelet, `op` amely `op(input)` azonos az `fn(input)` összes esetében `input` .</span><span class="sxs-lookup"><span data-stu-id="ada7d-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ada7d-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="ada7d-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="ada7d-114">"Bemenet</span><span class="sxs-lookup"><span data-stu-id="ada7d-114">'Input</span></span>

<span data-ttu-id="ada7d-115">Az átalakítandó függvény bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="ada7d-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="ada7d-116">"Output</span><span class="sxs-lookup"><span data-stu-id="ada7d-116">'Output</span></span>

<span data-ttu-id="ada7d-117">Az átalakítandó függvény kimeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="ada7d-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="ada7d-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="ada7d-118">Remarks</span></span>

<span data-ttu-id="ada7d-119">Ez különösen hasznos a függvények olyan függvényekhez vagy műveletekhez való átadásához, amelyek bemenetként egy műveletet várnak.</span><span class="sxs-lookup"><span data-stu-id="ada7d-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>