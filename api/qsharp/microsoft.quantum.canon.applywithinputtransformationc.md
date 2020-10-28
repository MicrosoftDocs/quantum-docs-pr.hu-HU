---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationC
title: ApplyWithInputTransformationC művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationC
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: f166880d3ca8a7fc45635c0105aa5c83fe1b4f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716846"
---
# <a name="applywithinputtransformationc-operation"></a><span data-ttu-id="29ebd-102">ApplyWithInputTransformationC művelet</span><span class="sxs-lookup"><span data-stu-id="29ebd-102">ApplyWithInputTransformationC operation</span></span>

<span data-ttu-id="29ebd-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="29ebd-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="29ebd-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="29ebd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="29ebd-105">Egy olyan művelet, amely egy bizonyos bemenetet fogad el, egy olyan függvényt ad vissza, amely kompatibilis a művelettel, és a függvény bemenete a művelettel a művelet által várt űrlapra alakítja át a bemenetet.</span><span class="sxs-lookup"><span data-stu-id="29ebd-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="29ebd-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="29ebd-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="29ebd-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="29ebd-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="29ebd-108">Függvény, amely átalakítja a megadott bemenetet a művelet által várt űrlapra.</span><span class="sxs-lookup"><span data-stu-id="29ebd-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="29ebd-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="29ebd-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="29ebd-110">Az alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="29ebd-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="29ebd-111">bemenet: U</span><span class="sxs-lookup"><span data-stu-id="29ebd-111">input : 'U</span></span>

<span data-ttu-id="29ebd-112">A függvény bemenete.</span><span class="sxs-lookup"><span data-stu-id="29ebd-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="29ebd-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="29ebd-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="29ebd-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="29ebd-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="29ebd-115">Nem</span><span class="sxs-lookup"><span data-stu-id="29ebd-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="29ebd-116">' U</span><span class="sxs-lookup"><span data-stu-id="29ebd-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="29ebd-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="29ebd-117">See Also</span></span>

- [<span data-ttu-id="29ebd-118">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="29ebd-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="29ebd-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="29ebd-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="29ebd-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="29ebd-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="29ebd-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="29ebd-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)