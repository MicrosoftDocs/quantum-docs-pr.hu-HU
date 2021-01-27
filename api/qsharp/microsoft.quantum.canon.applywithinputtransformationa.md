---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationA
title: ApplyWithInputTransformationA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: 3ab07f301f310e3ec380981bdb53201fc74bd289
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841122"
---
# <a name="applywithinputtransformationa-operation"></a><span data-ttu-id="f9ac9-102">ApplyWithInputTransformationA művelet</span><span class="sxs-lookup"><span data-stu-id="f9ac9-102">ApplyWithInputTransformationA operation</span></span>

<span data-ttu-id="f9ac9-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f9ac9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f9ac9-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9ac9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9ac9-105">Egy olyan művelet, amely egy bizonyos bemenetet fogad el, egy olyan függvényt ad vissza, amely kompatibilis a művelettel, és a függvény bemenete a művelettel a művelet által várt űrlapra alakítja át a bemenetet.</span><span class="sxs-lookup"><span data-stu-id="f9ac9-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj), input : 'U) : Unit is Adj
```


## <a name="input"></a><span data-ttu-id="f9ac9-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f9ac9-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="f9ac9-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="f9ac9-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="f9ac9-108">Függvény, amely átalakítja a megadott bemenetet a művelet által várt űrlapra.</span><span class="sxs-lookup"><span data-stu-id="f9ac9-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="f9ac9-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9ac9-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f9ac9-110">Az alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="f9ac9-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="f9ac9-111">bemenet: U</span><span class="sxs-lookup"><span data-stu-id="f9ac9-111">input : 'U</span></span>

<span data-ttu-id="f9ac9-112">A függvény bemenete.</span><span class="sxs-lookup"><span data-stu-id="f9ac9-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f9ac9-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f9ac9-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f9ac9-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="f9ac9-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f9ac9-115">Nem</span><span class="sxs-lookup"><span data-stu-id="f9ac9-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="f9ac9-116">' U</span><span class="sxs-lookup"><span data-stu-id="f9ac9-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="f9ac9-117">Példa</span><span class="sxs-lookup"><span data-stu-id="f9ac9-117">Example</span></span>

<span data-ttu-id="f9ac9-118">A következő hívás @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" egy olyan művelet alkalmazására szolgál, amely @"Microsoft.Quantum.Arithmetic.BigEndian" bemenetekhez van hozzárendelve egy típusú bemenethez @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="f9ac9-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="f9ac9-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="f9ac9-119">See Also</span></span>

- [<span data-ttu-id="f9ac9-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="f9ac9-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="f9ac9-121">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="f9ac9-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="f9ac9-122">Microsoft. Quantum. Canon. ApplyWithInputTransformationCA</span><span class="sxs-lookup"><span data-stu-id="f9ac9-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationCA)
- [<span data-ttu-id="f9ac9-123">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="f9ac9-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)