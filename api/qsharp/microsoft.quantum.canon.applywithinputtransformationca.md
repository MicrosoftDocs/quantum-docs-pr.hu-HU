---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: ApplyWithInputTransformationCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: c81620555bff9449d6a3235dc7cfa56ca5206f04
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207785"
---
# <a name="applywithinputtransformationca-operation"></a><span data-ttu-id="60da5-102">ApplyWithInputTransformationCA művelet</span><span class="sxs-lookup"><span data-stu-id="60da5-102">ApplyWithInputTransformationCA operation</span></span>

<span data-ttu-id="60da5-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="60da5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="60da5-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60da5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60da5-105">Egy olyan művelet, amely egy bizonyos bemenetet fogad el, egy olyan függvényt ad vissza, amely kompatibilis a művelettel, és a függvény bemenete a művelettel a művelet által várt űrlapra alakítja át a bemenetet.</span><span class="sxs-lookup"><span data-stu-id="60da5-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="60da5-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="60da5-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="60da5-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="60da5-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="60da5-108">Függvény, amely átalakítja a megadott bemenetet a művelet által várt űrlapra.</span><span class="sxs-lookup"><span data-stu-id="60da5-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="60da5-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="60da5-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="60da5-110">Az alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="60da5-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="60da5-111">bemenet: U</span><span class="sxs-lookup"><span data-stu-id="60da5-111">input : 'U</span></span>

<span data-ttu-id="60da5-112">A függvény bemenete.</span><span class="sxs-lookup"><span data-stu-id="60da5-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="60da5-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60da5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="60da5-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="60da5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="60da5-115">Nem</span><span class="sxs-lookup"><span data-stu-id="60da5-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="60da5-116">' U</span><span class="sxs-lookup"><span data-stu-id="60da5-116">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="60da5-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="60da5-117">See Also</span></span>

- [<span data-ttu-id="60da5-118">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="60da5-118">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="60da5-119">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="60da5-119">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="60da5-120">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="60da5-120">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="60da5-121">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="60da5-121">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)