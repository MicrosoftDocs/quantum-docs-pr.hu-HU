---
uid: Microsoft.Quantum.Canon.TransformedOperationA
title: TransformedOperationA függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TransformedOperationA
qsharp.summary: Given a function and an operation, returns a new operation whose input is transformed by the given function.
ms.openlocfilehash: fac0fb6e03dc515892783fb4a5fa9cfc274550b8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840146"
---
# <a name="transformedoperationa-function"></a><span data-ttu-id="d9d30-102">TransformedOperationA függvény</span><span class="sxs-lookup"><span data-stu-id="d9d30-102">TransformedOperationA function</span></span>

<span data-ttu-id="d9d30-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d9d30-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d9d30-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d9d30-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d9d30-105">Egy függvény és egy művelet miatt egy új műveletet ad vissza, amelynek a bemenetét az adott függvény átalakítja.</span><span class="sxs-lookup"><span data-stu-id="d9d30-105">Given a function and an operation, returns a new operation whose input is transformed by the given function.</span></span>

```qsharp
function TransformedOperationA<'T, 'U> (fn : ('U -> 'T), op : ('T => Unit is Adj)) : ('U => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="d9d30-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d9d30-106">Input</span></span>

### <a name="fn--u---t"></a><span data-ttu-id="d9d30-107">FN: U-> 'T</span><span class="sxs-lookup"><span data-stu-id="d9d30-107">fn : 'U -> 'T</span></span>

<span data-ttu-id="d9d30-108">Függvény, amely átalakítja a megadott bemenetet a művelet által várt űrlapra.</span><span class="sxs-lookup"><span data-stu-id="d9d30-108">A function that transforms the given input into a form expected by the operation.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="d9d30-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d9d30-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d9d30-110">Az átalakítandó művelet.</span><span class="sxs-lookup"><span data-stu-id="d9d30-110">The operation to be transformed.</span></span>



## <a name="output--u--unit--is-adj"></a><span data-ttu-id="d9d30-111">Kimenet: ' U => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d9d30-111">Output : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="d9d30-112">Egy új művelet tbat hívja a `fn` bemenetét, majd átadja az eredményül kapott kimenetet `op` .</span><span class="sxs-lookup"><span data-stu-id="d9d30-112">A new operation tbat calls `fn` with its input, then passes the resulting output to `op`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d9d30-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="d9d30-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d9d30-114">Nem</span><span class="sxs-lookup"><span data-stu-id="d9d30-114">'T</span></span>


### <a name="u"></a><span data-ttu-id="d9d30-115">' U</span><span class="sxs-lookup"><span data-stu-id="d9d30-115">'U</span></span>



## <a name="example"></a><span data-ttu-id="d9d30-116">Példa</span><span class="sxs-lookup"><span data-stu-id="d9d30-116">Example</span></span>

<span data-ttu-id="d9d30-117">A következő hívás @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" egy olyan művelet átalakítására szolgál, amelynek @"Microsoft.Quantum.Arithmetic.BigEndian" bemenetei egy olyan műveletbe kerülnek, amely a típusú bemeneteket fogadja el @"Microsoft.Quantum.Arithmetic.LittleEndian" :</span><span class="sxs-lookup"><span data-stu-id="d9d30-117">The following call uses @"Microsoft.Quantum.Arithmetic.LittleEndianAsBigEndian" to transform an operation designed for @"Microsoft.Quantum.Arithmetic.BigEndian" inputs into an operation that accepts inputs of type @"Microsoft.Quantum.Arithmetic.LittleEndian":</span></span>

```qsharp
let leOp = TransformedOperation(LittleEndianAsBigEndian, ApplyXorInPlaceBE);
```

## <a name="see-also"></a><span data-ttu-id="d9d30-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="d9d30-118">See Also</span></span>

- [<span data-ttu-id="d9d30-119">Microsoft. Quantum. Canon. TransformedOperation</span><span class="sxs-lookup"><span data-stu-id="d9d30-119">Microsoft.Quantum.Canon.TransformedOperation</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperation)
- [<span data-ttu-id="d9d30-120">Microsoft. Quantum. Canon. TransformedOperationC</span><span class="sxs-lookup"><span data-stu-id="d9d30-120">Microsoft.Quantum.Canon.TransformedOperationC</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationC)
- [<span data-ttu-id="d9d30-121">Microsoft. Quantum. Canon. TransformedOperationCA</span><span class="sxs-lookup"><span data-stu-id="d9d30-121">Microsoft.Quantum.Canon.TransformedOperationCA</span></span>](xref:Microsoft.Quantum.Canon.TransformedOperationCA)
- [<span data-ttu-id="d9d30-122">Microsoft. Quantum. Canon. ApplyWithInputTransformation</span><span class="sxs-lookup"><span data-stu-id="d9d30-122">Microsoft.Quantum.Canon.ApplyWithInputTransformation</span></span>](xref:Microsoft.Quantum.Canon.ApplyWithInputTransformation)
- [<span data-ttu-id="d9d30-123">Microsoft. Quantum. Canon. komponált</span><span class="sxs-lookup"><span data-stu-id="d9d30-123">Microsoft.Quantum.Canon.Composed</span></span>](xref:Microsoft.Quantum.Canon.Composed)