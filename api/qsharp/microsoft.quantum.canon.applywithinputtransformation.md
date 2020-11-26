---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformation
title: ApplyWithInputTransformation művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformation
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 3586e9a114a550fb1989186e9c18fe4f344cf060
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217186"
---
# <a name="applywithinputtransformation-operation"></a><span data-ttu-id="8003a-102">ApplyWithInputTransformation művelet</span><span class="sxs-lookup"><span data-stu-id="8003a-102">ApplyWithInputTransformation operation</span></span>

<span data-ttu-id="8003a-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8003a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8003a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8003a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8003a-105">Egy olyan művelet, amely egy bizonyos bemenetet fogad el, egy olyan függvényt ad vissza, amely kompatibilis a művelettel, és a függvény bemenete a művelettel a művelet által várt űrlapra alakítja át a bemenetet.</span><span class="sxs-lookup"><span data-stu-id="8003a-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit), input : 'U) : Unit
```


## <a name="input"></a><span data-ttu-id="8003a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8003a-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="8003a-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="8003a-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="8003a-108">Függvény, amely átalakítja a megadott bemenetet a művelet által várt űrlapra.</span><span class="sxs-lookup"><span data-stu-id="8003a-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="8003a-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8003a-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="8003a-110">Az alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="8003a-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="8003a-111">bemenet: U</span><span class="sxs-lookup"><span data-stu-id="8003a-111">input : 'U</span></span>

<span data-ttu-id="8003a-112">A függvény bemenete.</span><span class="sxs-lookup"><span data-stu-id="8003a-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8003a-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8003a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8003a-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="8003a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8003a-115">Nem</span><span class="sxs-lookup"><span data-stu-id="8003a-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="8003a-116">' U</span><span class="sxs-lookup"><span data-stu-id="8003a-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="8003a-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="8003a-117">See Also</span></span>

- [<span data-ttu-id="8003a-118">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="8003a-118">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="8003a-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="8003a-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="8003a-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="8003a-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="8003a-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="8003a-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)