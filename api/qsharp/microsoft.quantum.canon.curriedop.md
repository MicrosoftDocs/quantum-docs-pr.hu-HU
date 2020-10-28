---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 13bc3e195d8a4ba26b726f96e4dc6b83da43c3e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716370"
---
# <a name="curriedop-function"></a><span data-ttu-id="2802a-102">CurriedOp függvény</span><span class="sxs-lookup"><span data-stu-id="2802a-102">CurriedOp function</span></span>

<span data-ttu-id="2802a-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2802a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2802a-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2802a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2802a-105">Egy művelet egy két bemenetén lévő, a művelethez tartozó, Currie-beli verzióját adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2802a-105">Returns a curried version of an operation on two inputs.</span></span>

<span data-ttu-id="2802a-106">Ez azt eredményezi, hogy a művelet két bemenettel rendelkezik, ez a függvény a curry isomorphism $f (x, y) \equiv f (x) (y) $-t alkalmazza egy olyan bemenet műveletének visszaadására, amely egy bemenet műveletét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="2802a-106">That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.</span></span>

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a><span data-ttu-id="2802a-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2802a-107">Input</span></span>

### <a name="op--tu--unit"></a><span data-ttu-id="2802a-108">op: (nem, ' U) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2802a-108">op : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2802a-109">Olyan művelet, amelynek bemenete egy pár.</span><span class="sxs-lookup"><span data-stu-id="2802a-109">An operation whose input is a pair.</span></span>



## <a name="output--t---u--unit"></a><span data-ttu-id="2802a-110">Kimenet: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2802a-110">Output : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="2802a-111">Egy olyan művelet, amely egy pár első elemét fogadja, és egy olyan műveletet ad vissza, amely az eredeti művelet bemenetének második elemeként fogadja el.</span><span class="sxs-lookup"><span data-stu-id="2802a-111">An operation which accepts the first element of a pair and returns an operation which accepts as its input the second element of the original operation's input.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2802a-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2802a-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2802a-113">Nem</span><span class="sxs-lookup"><span data-stu-id="2802a-113">'T</span></span>

<span data-ttu-id="2802a-114">A párokban definiált függvény első összetevőjének típusa.</span><span class="sxs-lookup"><span data-stu-id="2802a-114">The type of the first component of a function defined on pairs.</span></span>
### <a name="u"></a><span data-ttu-id="2802a-115">' U</span><span class="sxs-lookup"><span data-stu-id="2802a-115">'U</span></span>

<span data-ttu-id="2802a-116">A párokban definiált függvény második összetevőjének típusa.</span><span class="sxs-lookup"><span data-stu-id="2802a-116">The type of the second component of a function defined on pairs.</span></span>

## <a name="remarks"></a><span data-ttu-id="2802a-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="2802a-117">Remarks</span></span>

<span data-ttu-id="2802a-118">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="2802a-118">The following are equivalent:</span></span>

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```