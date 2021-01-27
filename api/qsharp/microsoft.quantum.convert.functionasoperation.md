---
uid: Microsoft.Quantum.Convert.FunctionAsOperation
title: FunctionAsOperation függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: FunctionAsOperation
qsharp.summary: Converts functions to operations.
ms.openlocfilehash: cf4f8c97bf38b3a64eb952d0a502bc21c29c579c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833840"
---
# <a name="functionasoperation-function"></a><span data-ttu-id="6de6f-102">FunctionAsOperation függvény</span><span class="sxs-lookup"><span data-stu-id="6de6f-102">FunctionAsOperation function</span></span>

<span data-ttu-id="6de6f-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="6de6f-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="6de6f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6de6f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6de6f-105">Átalakítja a függvényeket a műveletekre.</span><span class="sxs-lookup"><span data-stu-id="6de6f-105">Converts functions to operations.</span></span>

```qsharp
function FunctionAsOperation<'Input, 'Output> (fn : ('Input -> 'Output)) : ('Input => 'Output)
```


## <a name="description"></a><span data-ttu-id="6de6f-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="6de6f-106">Description</span></span>

<span data-ttu-id="6de6f-107">A függvény adott funkciója olyan műveletet ad vissza, amely meghívja a függvényt, és amely nem más.</span><span class="sxs-lookup"><span data-stu-id="6de6f-107">Given a function, returns an operation which calls that function, and which does nothing else.</span></span>

## <a name="input"></a><span data-ttu-id="6de6f-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6de6f-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="6de6f-109">FN: "input->" kimenet</span><span class="sxs-lookup"><span data-stu-id="6de6f-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="6de6f-110">Egy műveletre konvertálandó függvény.</span><span class="sxs-lookup"><span data-stu-id="6de6f-110">A function to be converted to an operation.</span></span>



## <a name="output--input--output"></a><span data-ttu-id="6de6f-111">Kimenet: "input =>" kimenet</span><span class="sxs-lookup"><span data-stu-id="6de6f-111">Output : 'Input => 'Output</span></span> 

<span data-ttu-id="6de6f-112">Olyan művelet, `op` amely `op(input)` azonos az `fn(input)` összes esetében `input` .</span><span class="sxs-lookup"><span data-stu-id="6de6f-112">An operation `op` such that `op(input)` is identical to `fn(input)` for all `input`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6de6f-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="6de6f-113">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="6de6f-114">"Bemenet</span><span class="sxs-lookup"><span data-stu-id="6de6f-114">'Input</span></span>

<span data-ttu-id="6de6f-115">Az átalakítandó függvény bemeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="6de6f-115">Input type of the function to be converted.</span></span>
### <a name="output"></a><span data-ttu-id="6de6f-116">"Output</span><span class="sxs-lookup"><span data-stu-id="6de6f-116">'Output</span></span>

<span data-ttu-id="6de6f-117">Az átalakítandó függvény kimeneti típusa.</span><span class="sxs-lookup"><span data-stu-id="6de6f-117">Output type of the function to be converted.</span></span>

## <a name="remarks"></a><span data-ttu-id="6de6f-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="6de6f-118">Remarks</span></span>

<span data-ttu-id="6de6f-119">Ez különösen hasznos a függvények olyan függvényekhez vagy műveletekhez való átadásához, amelyek bemenetként egy műveletet várnak.</span><span class="sxs-lookup"><span data-stu-id="6de6f-119">This is mainly useful for passing functions to functions or operations which expect an operation as input.</span></span>