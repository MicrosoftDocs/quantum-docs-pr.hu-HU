---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: 10703818242cf6b3853f08a45bfb9094f397f6c2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224377"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="1b25c-102">FunctionAsOperation függvény</span><span class="sxs-lookup"><span data-stu-id="1b25c-102">FunctionAsOperation function</span></span>

<span data-ttu-id="1b25c-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="1b25c-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="1b25c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b25c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1b25c-105">Átalakítja a függvényeket a műveletekre.</span><span class="sxs-lookup"><span data-stu-id="1b25c-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="1b25c-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="1b25c-106">Description</span></span>

<span data-ttu-id="1b25c-107">A függvény adott funkciója olyan műveletet ad vissza, amely meghívja a függvényt, és amely nem más.</span><span class="sxs-lookup"><span data-stu-id="1b25c-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="1b25c-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1b25c-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="1b25c-109">FN: "input->" kimenet</span><span class="sxs-lookup"><span data-stu-id="1b25c-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="1b25c-110">Egy műveletre konvertálandó függvény.</span><span class="sxs-lookup"><span data-stu-id="1b25c-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="1b25c-111">Kimenet: "input =>" kimenet</span><span class="sxs-lookup"><span data-stu-id="1b25c-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="1b25c-112">Olyan művelet, `op` amely `op(input)` azonos az `fn(input)` összes esetében `input` .</span><span class="sxs-lookup"><span data-stu-id="1b25c-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1b25c-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="1b25c-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="1b25c-114">"Bemenet</span><span class="sxs-lookup"><span data-stu-id="1b25c-114">'Input</span></span>

<span data-ttu-id="1b25c-115">Az átalakítandó függvény bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="1b25c-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="1b25c-116">"Output</span><span class="sxs-lookup"><span data-stu-id="1b25c-116">'Output</span></span>

<span data-ttu-id="1b25c-117">Az átalakítandó függvény kimeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="1b25c-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b25c-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="1b25c-118">Remarks</span></span>

<span data-ttu-id="1b25c-119">Ez különösen hasznos a függvények olyan függvényekhez vagy műveletekhez való átadásához, amelyek bemenetként egy műveletet várnak.</span><span class="sxs-lookup"><span data-stu-id="1b25c-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>