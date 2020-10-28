---
uid: Microsoft.Quantum.Canon.TransformedOperationC
title: TransformedOperationC függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationC
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: b6867a076b654337f6127657189a8453c9973cc2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715321"
---
# <a name="transformedoperationc-function"></a><span data-ttu-id="f6570-102">TransformedOperationC függvény</span><span class="sxs-lookup"><span data-stu-id="f6570-102">TransformedOperationC function</span></span>

<span data-ttu-id="f6570-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f6570-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f6570-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f6570-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f6570-105">Egy függvény és egy művelet miatt egy új műveletet ad vissza, amelynek a bemenetét az adott függvény átalakítja.</span><span class="sxs-lookup"><span data-stu-id="f6570-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl)) : ('U => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="f6570-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f6570-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="f6570-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="f6570-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="f6570-108">Függvény, amely átalakítja a megadott bemenetet a művelet által várt űrlapra.</span><span class="sxs-lookup"><span data-stu-id="f6570-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit-ctl"></a><span data-ttu-id="f6570-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="f6570-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="f6570-110">Az átalakítandó művelet.</span><span class="sxs-lookup"><span data-stu-id="f6570-110">The operation to be transformed.</span></span>



## <a name="output--u--unit-ctl"></a><span data-ttu-id="f6570-111">Kimenet: ' U => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="f6570-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="f6570-112">Egy új művelet tbat hívja a `fn` bemenetét, majd átadja az eredményül kapott kimenetet `op` .</span><span class="sxs-lookup"><span data-stu-id="f6570-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f6570-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="f6570-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f6570-114">Nem</span><span class="sxs-lookup"><span data-stu-id="f6570-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="f6570-115">' U</span><span class="sxs-lookup"><span data-stu-id="f6570-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="f6570-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="f6570-116">See Also</span></span>

- [<span data-ttu-id="f6570-117">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="f6570-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="f6570-118">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="f6570-118">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="f6570-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="f6570-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="f6570-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="f6570-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="f6570-121">Microsoft. Quantum. Canon. komponált</span><span class="sxs-lookup"><span data-stu-id="f6570-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)