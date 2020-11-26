---
uid: Microsoft.Quantum.Canon.TransformedOperationC
title: TransformedOperationC függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationC
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: 964576788bc80dd8920acdfb62d5d69a060e75f6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204861"
---
# <a name="transformedoperationc-function"></a><span data-ttu-id="ca7e5-102">TransformedOperationC függvény</span><span class="sxs-lookup"><span data-stu-id="ca7e5-102">TransformedOperationC function</span></span>

<span data-ttu-id="ca7e5-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ca7e5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ca7e5-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ca7e5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ca7e5-105">Egy függvény és egy művelet miatt egy új műveletet ad vissza, amelynek a bemenetét az adott függvény átalakítja.</span><span class="sxs-lookup"><span data-stu-id="ca7e5-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationC<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Ctl)) : ('U => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="ca7e5-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ca7e5-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="ca7e5-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="ca7e5-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="ca7e5-108">Függvény, amely átalakítja a megadott bemenetet a művelet által várt űrlapra.</span><span class="sxs-lookup"><span data-stu-id="ca7e5-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="ca7e5-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="ca7e5-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="ca7e5-110">Az átalakítandó művelet.</span><span class="sxs-lookup"><span data-stu-id="ca7e5-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-ctl"></a><span data-ttu-id="ca7e5-111">Kimenet: ' U => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="ca7e5-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="ca7e5-112">Egy új művelet tbat hívja a `fn` bemenetét, majd átadja az eredményül kapott kimenetet `op` .</span><span class="sxs-lookup"><span data-stu-id="ca7e5-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ca7e5-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="ca7e5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ca7e5-114">Nem</span><span class="sxs-lookup"><span data-stu-id="ca7e5-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="ca7e5-115">' U</span><span class="sxs-lookup"><span data-stu-id="ca7e5-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="ca7e5-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="ca7e5-116">See Also</span></span>

- [<span data-ttu-id="ca7e5-117">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="ca7e5-117">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="ca7e5-118">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="ca7e5-118">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="ca7e5-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="ca7e5-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="ca7e5-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="ca7e5-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="ca7e5-121">Microsoft. Quantum. Canon. komponált</span><span class="sxs-lookup"><span data-stu-id="ca7e5-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)