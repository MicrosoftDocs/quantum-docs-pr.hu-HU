---
uid: Microsoft.Quantum.Canon.ApplyWithInputTransformationCA
title: ApplyWithInputTransformationCA művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyWithInputTransformationCA
qsharp.summary: Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.
ms.openlocfilehash: b31ed1b3da0d5467588f4cb2e4368e68f0dbe9d5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841118"
---
# <a name="applywithinputtransformationca-operation"></a><span data-ttu-id="7ec70-102">ApplyWithInputTransformationCA művelet</span><span class="sxs-lookup"><span data-stu-id="7ec70-102">ApplyWithInputTransformationCA operation</span></span>

<span data-ttu-id="7ec70-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7ec70-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7ec70-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7ec70-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7ec70-105">Egy olyan művelet, amely egy bizonyos bemenetet fogad el, egy olyan függvényt ad vissza, amely kompatibilis a művelettel, és a függvény bemenete a művelettel a művelet által várt űrlapra alakítja át a bemenetet.</span><span class="sxs-lookup"><span data-stu-id="7ec70-105">Given an operation that accepts some input, a function that returns an output compatible with that operation, and an input to that function, applies the operation using the function to transform the input to a form expected by the operation.</span></span>

```qsharp
operation ApplyWithInputTransformationCA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj + Ctl), input : 'U) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="7ec70-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7ec70-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="7ec70-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="7ec70-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="7ec70-108">Függvény, amely átalakítja a megadott bemenetet a művelet által várt űrlapra.</span><span class="sxs-lookup"><span data-stu-id="7ec70-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="7ec70-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="7ec70-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="7ec70-110">Az alkalmazni kívánt művelet.</span><span class="sxs-lookup"><span data-stu-id="7ec70-110">The operation to be applied.</span></span>


### <a name="input--u"></a><span data-ttu-id="7ec70-111">bemenet: U</span><span class="sxs-lookup"><span data-stu-id="7ec70-111">input : 'U</span></span>

<span data-ttu-id="7ec70-112">A függvény bemenete.</span><span class="sxs-lookup"><span data-stu-id="7ec70-112">An input to the function.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7ec70-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7ec70-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7ec70-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="7ec70-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7ec70-115">Nem</span><span class="sxs-lookup"><span data-stu-id="7ec70-115">'T</span></span>


### <a name="u"></a><span data-ttu-id="7ec70-116">' U</span><span class="sxs-lookup"><span data-stu-id="7ec70-116">'U</span></span>



## <a name="example"></a><span data-ttu-id="7ec70-117">Példa</span><span class="sxs-lookup"><span data-stu-id="7ec70-117">Example</span></span>

<span data-ttu-id="7ec70-118">A következő hívás @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" egy olyan művelet alkalmazására szolgál, amely @"Microsoft.Quantum.Arithmetic.BigEndian" bemenetekhez van hozzárendelve egy típusú bemenethez @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="7ec70-118">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to apply an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs to an input of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
ApplyWithInputTransformation(LittleEndianAsBigEndian, ApplyXorInPlaceBE, LittleEndian(qubits));
```

## <a name="see-also"></a><span data-ttu-id="7ec70-119">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="7ec70-119">See Also</span></span>

- [<span data-ttu-id="7ec70-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="7ec70-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="7ec70-121">Microsoft. Quantum. Canon. ApplyWithInputTransformationA</span><span class="sxs-lookup"><span data-stu-id="7ec70-121">Microsoft.Quantum.Canon.ApplyWithInputTransformationA</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationA)
- [<span data-ttu-id="7ec70-122">Microsoft. Quantum. Canon. ApplyWithInputTransformationC</span><span class="sxs-lookup"><span data-stu-id="7ec70-122">Microsoft.Quantum.Canon.ApplyWithInputTransformationC</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformationC)
- [<span data-ttu-id="7ec70-123">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="7ec70-123">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)