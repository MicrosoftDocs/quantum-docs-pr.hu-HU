---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: a26cc178f67fd99324355ac230d9e91081b6e238
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204929"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="c579c-102">TransformedOperation függvény</span><span class="sxs-lookup"><span data-stu-id="c579c-102">TransformedOperation function</span></span>

<span data-ttu-id="c579c-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c579c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c579c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c579c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c579c-105">Egy függvény és egy művelet miatt egy új műveletet ad vissza, amelynek a bemenetét az adott függvény átalakítja.</span><span class="sxs-lookup"><span data-stu-id="c579c-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="c579c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c579c-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="c579c-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="c579c-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="c579c-108">Függvény, amely átalakítja a megadott bemenetet a művelet által várt űrlapra.</span><span class="sxs-lookup"><span data-stu-id="c579c-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="c579c-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c579c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c579c-110">Az átalakítandó művelet.</span><span class="sxs-lookup"><span data-stu-id="c579c-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="c579c-111">Kimenet: ' U => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c579c-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c579c-112">Egy új művelet tbat hívja a `fn` bemenetét, majd átadja az eredményül kapott kimenetet `op` .</span><span class="sxs-lookup"><span data-stu-id="c579c-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c579c-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c579c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c579c-114">Nem</span><span class="sxs-lookup"><span data-stu-id="c579c-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="c579c-115">' U</span><span class="sxs-lookup"><span data-stu-id="c579c-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="c579c-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="c579c-116">See Also</span></span>

- [<span data-ttu-id="c579c-117">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="c579c-117">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="c579c-118">Microsoft. Quantum. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="c579c-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="c579c-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="c579c-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="c579c-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="c579c-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="c579c-121">Microsoft. Quantum. Canon. komponált</span><span class="sxs-lookup"><span data-stu-id="c579c-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)