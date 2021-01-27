---
uid: Microsoft.Quantum.Convert.Call
title: Hívási művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: Call
qsharp.summary: Calls a function with a given input.
ms.openlocfilehash: 93458d08aa83ffa8b7b33de8bf51c970af291db9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850198"
---
# <a name="call-operation"></a><span data-ttu-id="8b4b8-102">Hívási művelet</span><span class="sxs-lookup"><span data-stu-id="8b4b8-102">Call operation</span></span>

<span data-ttu-id="8b4b8-103">Névtér: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="8b4b8-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="8b4b8-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8b4b8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8b4b8-105">Egy függvényt hív meg egy megadott bemenettel.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-105">Calls a function with a given input.</span></span>

```qsharp
operation Call<'Input, 'Output> (fn : ('Input -> 'Output), input : 'Input) : 'Output
```


## <a name="description"></a><span data-ttu-id="8b4b8-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="8b4b8-106">Description</span></span>

<span data-ttu-id="8b4b8-107">Az adott függvény és a függvény bemenete meghívja a függvényt, és visszaadja a kimenetét.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-107">Given a function and an input to that function, calls the function and returns its output.</span></span>

## <a name="input"></a><span data-ttu-id="8b4b8-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8b4b8-108">Input</span></span>

### <a name="fn--input---output"></a><span data-ttu-id="8b4b8-109">FN: "input->" kimenet</span><span class="sxs-lookup"><span data-stu-id="8b4b8-109">fn : 'Input -> 'Output</span></span>

<span data-ttu-id="8b4b8-110">Egy meghívható függvény.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-110">A function to be called.</span></span>


### <a name="input--input"></a><span data-ttu-id="8b4b8-111">bemenet: bemenet</span><span class="sxs-lookup"><span data-stu-id="8b4b8-111">input : 'Input</span></span>

<span data-ttu-id="8b4b8-112">A függvénynek átadandó bemenet.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-112">The input to be passed to the function.</span></span>



## <a name="output--output"></a><span data-ttu-id="8b4b8-113">Kimenet: kimenet</span><span class="sxs-lookup"><span data-stu-id="8b4b8-113">Output : 'Output</span></span>

<span data-ttu-id="8b4b8-114">A hívás eredménye `fn` .</span><span class="sxs-lookup"><span data-stu-id="8b4b8-114">The result of calling `fn`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8b4b8-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="8b4b8-115">Type Parameters</span></span>

### <a name="input"></a><span data-ttu-id="8b4b8-116">"Bemenet</span><span class="sxs-lookup"><span data-stu-id="8b4b8-116">'Input</span></span>


### <a name="output"></a><span data-ttu-id="8b4b8-117">"Output</span><span class="sxs-lookup"><span data-stu-id="8b4b8-117">'Output</span></span>



## <a name="remarks"></a><span data-ttu-id="8b4b8-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="8b4b8-118">Remarks</span></span>

<span data-ttu-id="8b4b8-119">Ez a művelet különösen hasznos ahhoz, hogy a függvényt egy adott helyen lehessen meghívni egy műveleten belül, vagy egy olyan függvény meghívásához, amelyben a művelet várható.</span><span class="sxs-lookup"><span data-stu-id="8b4b8-119">This operation is mainly useful for forcing a function to be called at a specific place within an operation, or for calling a function where an operation is expected.</span></span>