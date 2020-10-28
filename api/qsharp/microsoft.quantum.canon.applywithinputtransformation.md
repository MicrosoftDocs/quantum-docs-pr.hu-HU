---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: ApplyWithInputTransformation művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 2b7863337ef724d9c3ba10201a9a01d0b2226ea8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716861"
---
# <a name="applywithinputtransformation-operation"></a><span data-ttu-id="2402c-102">ApplyWithInputTransformation művelet</span><span class="sxs-lookup"><span data-stu-id="2402c-102">ApplyWithInputTransformation operation</span></span>

<span data-ttu-id="2402c-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2402c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2402c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2402c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2402c-105">Egy olyan művelet, amely egy bizonyos bemenetet fogad el, egy olyan függvényt ad vissza, amely kompatibilis a művelettel, és a függvény bemenete a művelettel a művelet által várt űrlapra alakítja át a bemenetet.</span><span class="sxs-lookup"><span data-stu-id="2402c-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="2402c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2402c-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="2402c-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="2402c-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="2402c-108">Függvény, amely átalakítja a megadott bemenetet a művelet által várt űrlapra.</span><span class="sxs-lookup"><span data-stu-id="2402c-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="2402c-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2402c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2402c-110">Az alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="2402c-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="2402c-111">bemenet: U</span><span class="sxs-lookup"><span data-stu-id="2402c-111">input : 'U</span></span>

<span data-ttu-id="2402c-112">A függvény bemenete.</span><span class="sxs-lookup"><span data-stu-id="2402c-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2402c-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2402c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2402c-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2402c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2402c-115">Nem</span><span class="sxs-lookup"><span data-stu-id="2402c-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="2402c-116">' U</span><span class="sxs-lookup"><span data-stu-id="2402c-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="2402c-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="2402c-117">See Also</span></span>

- [<span data-ttu-id="2402c-118">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="2402c-118">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="2402c-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="2402c-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="2402c-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="2402c-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="2402c-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="2402c-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)