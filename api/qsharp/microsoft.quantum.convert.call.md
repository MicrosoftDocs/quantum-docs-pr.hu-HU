---
uid: Microsoft.Quantum.Convert.Call
title: Hívási művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 8630f846b4b9823ce1c1dfd61dc8ca81e468517d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713529"
---
# <a name="call-operation"></a><span data-ttu-id="00918-102">Hívási művelet</span><span class="sxs-lookup"><span data-stu-id="00918-102">Call operation</span></span>

<span data-ttu-id="00918-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="00918-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="00918-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="00918-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="00918-105">Egy függvényt hív meg egy megadott bemenettel.</span><span class="sxs-lookup"><span data-stu-id="00918-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="00918-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="00918-106">Description</span></span>

<span data-ttu-id="00918-107">Az adott függvény és a függvény bemenete meghívja a függvényt, és visszaadja a kimenetét.</span><span class="sxs-lookup"><span data-stu-id="00918-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="00918-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="00918-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="00918-109">FN: "input->" kimenet</span><span class="sxs-lookup"><span data-stu-id="00918-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="00918-110">Egy meghívható függvény.</span><span class="sxs-lookup"><span data-stu-id="00918-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="00918-111">bemenet: bemenet</span><span class="sxs-lookup"><span data-stu-id="00918-111">input : 'Input</span></span>

<span data-ttu-id="00918-112">A függvénynek átadandó bemenet.</span><span class="sxs-lookup"><span data-stu-id="00918-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="00918-113">Kimenet: kimenet</span><span class="sxs-lookup"><span data-stu-id="00918-113">Output : 'Output</span></span>

<span data-ttu-id="00918-114">A hívás eredménye `fn` .</span><span class="sxs-lookup"><span data-stu-id="00918-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="00918-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="00918-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="00918-116">"Bemenet</span><span class="sxs-lookup"><span data-stu-id="00918-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="00918-117">"Output</span><span class="sxs-lookup"><span data-stu-id="00918-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="00918-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="00918-118">Remarks</span></span>

<span data-ttu-id="00918-119">Ez a művelet különösen hasznos ahhoz, hogy a függvényt egy adott helyen lehessen meghívni egy műveleten belül, vagy egy olyan függvény meghívásához, amelyben a művelet várható.</span><span class="sxs-lookup"><span data-stu-id="00918-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>