---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: ApplyWithInputTransformationA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: b72c131691e08b4bd32b7faf9265aad6c52b7fde
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716847"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="64d30-102">ApplyWithInputTransformationA művelet</span><span class="sxs-lookup"><span data-stu-id="64d30-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="64d30-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="64d30-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="64d30-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="64d30-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="64d30-105">Egy olyan művelet, amely egy bizonyos bemenetet fogad el, egy olyan függvényt ad vissza, amely kompatibilis a művelettel, és a függvény bemenete a művelettel a művelet által várt űrlapra alakítja át a bemenetet.</span><span class="sxs-lookup"><span data-stu-id="64d30-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="64d30-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="64d30-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="64d30-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="64d30-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="64d30-108">Függvény, amely átalakítja a megadott bemenetet a művelet által várt űrlapra.</span><span class="sxs-lookup"><span data-stu-id="64d30-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="64d30-109">op: nem =>i [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="64d30-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="64d30-110">Az alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="64d30-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="64d30-111">bemenet: U</span><span class="sxs-lookup"><span data-stu-id="64d30-111">input : 'U</span></span>

<span data-ttu-id="64d30-112">A függvény bemenete.</span><span class="sxs-lookup"><span data-stu-id="64d30-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="64d30-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="64d30-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="64d30-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="64d30-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="64d30-115">Nem</span><span class="sxs-lookup"><span data-stu-id="64d30-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="64d30-116">' U</span><span class="sxs-lookup"><span data-stu-id="64d30-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="64d30-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="64d30-117">See Also</span></span>

- [<span data-ttu-id="64d30-118">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="64d30-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="64d30-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="64d30-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="64d30-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="64d30-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="64d30-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="64d30-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)