---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: ApplyWithInputTransformationA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 8d65af33a0bc8ce3c08da54b34e68b4e22b710ca
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207887"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="6b090-102">ApplyWithInputTransformationA művelet</span><span class="sxs-lookup"><span data-stu-id="6b090-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="6b090-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6b090-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6b090-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6b090-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6b090-105">Egy olyan művelet, amely egy bizonyos bemenetet fogad el, egy olyan függvényt ad vissza, amely kompatibilis a művelettel, és a függvény bemenete a művelettel a művelet által várt űrlapra alakítja át a bemenetet.</span><span class="sxs-lookup"><span data-stu-id="6b090-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="6b090-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6b090-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="6b090-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="6b090-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="6b090-108">Függvény, amely átalakítja a megadott bemenetet a művelet által várt űrlapra.</span><span class="sxs-lookup"><span data-stu-id="6b090-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="6b090-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b090-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="6b090-110">Az alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="6b090-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="6b090-111">bemenet: U</span><span class="sxs-lookup"><span data-stu-id="6b090-111">input : 'U</span></span>

<span data-ttu-id="6b090-112">A függvény bemenete.</span><span class="sxs-lookup"><span data-stu-id="6b090-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6b090-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6b090-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6b090-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="6b090-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6b090-115">Nem</span><span class="sxs-lookup"><span data-stu-id="6b090-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="6b090-116">' U</span><span class="sxs-lookup"><span data-stu-id="6b090-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="6b090-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="6b090-117">See Also</span></span>

- [<span data-ttu-id="6b090-118">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="6b090-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="6b090-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="6b090-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="6b090-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="6b090-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="6b090-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="6b090-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)