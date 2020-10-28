---
uid: Microsoft.Quantum.Canon.TransformedOperation
title: TransformedOperation függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperation
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: d8c2f52290ce89d0a8ff138ba25f6b2e5e0516d5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715335"
---
# <a name="transformedoperation-function"></a><span data-ttu-id="ca571-102">TransformedOperation függvény</span><span class="sxs-lookup"><span data-stu-id="ca571-102">TransformedOperation function</span></span>

<span data-ttu-id="ca571-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ca571-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ca571-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ca571-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ca571-105">Egy függvény és egy művelet miatt egy új műveletet ad vissza, amelynek a bemenetét az adott függvény átalakítja.</span><span class="sxs-lookup"><span data-stu-id="ca571-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperation<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit)) : ('U => Unit)
```


## <a name="input"></a><span data-ttu-id="ca571-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ca571-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="ca571-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="ca571-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="ca571-108">Függvény, amely átalakítja a megadott bemenetet a művelet által várt űrlapra.</span><span class="sxs-lookup"><span data-stu-id="ca571-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="ca571-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ca571-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ca571-110">Az átalakítandó művelet.</span><span class="sxs-lookup"><span data-stu-id="ca571-110">The operation to be transformed.</span></span>



## <a name="output--u--unit"></a><span data-ttu-id="ca571-111">Kimenet: ' U => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ca571-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="ca571-112">Egy új művelet tbat hívja a `fn` bemenetét, majd átadja az eredményül kapott kimenetet `op` .</span><span class="sxs-lookup"><span data-stu-id="ca571-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ca571-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="ca571-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ca571-114">Nem</span><span class="sxs-lookup"><span data-stu-id="ca571-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="ca571-115">' U</span><span class="sxs-lookup"><span data-stu-id="ca571-115">'U</span></span>



## <a name="see-also"></a><span data-ttu-id="ca571-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="ca571-116">See Also</span></span>

- [<span data-ttu-id="ca571-117">Microsoft. Quantum. Canon. TransformedOperationA</span><span class="sxs-lookup"><span data-stu-id="ca571-117">Microsoft.Quantum.Canon.TransformedOperationA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationA)
- [<span data-ttu-id="ca571-118">Microsoft. Quantum. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="ca571-118">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="ca571-119">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="ca571-119">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="ca571-120">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="ca571-120">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="ca571-121">Microsoft. Quantum. Canon. komponált</span><span class="sxs-lookup"><span data-stu-id="ca571-121">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)