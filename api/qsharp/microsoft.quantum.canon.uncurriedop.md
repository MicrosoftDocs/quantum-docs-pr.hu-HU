---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: d707b52bb17f4dea795fa4ff824c785e506b8b20
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852010"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="d8b81-102">UncurriedOp függvény</span><span class="sxs-lookup"><span data-stu-id="d8b81-102">UncurriedOp function</span></span>

<span data-ttu-id="d8b81-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d8b81-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d8b81-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d8b81-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d8b81-105">Egy olyan függvény, amely egy műveletet ad vissza, egy új műveletet ad vissza, amely mindkét bemenetet rekordként veszi át.</span><span class="sxs-lookup"><span data-stu-id="d8b81-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="d8b81-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d8b81-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="d8b81-107">curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d8b81-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d8b81-108">Egy függvény, amely visszaadja A műveleteket.</span><span class="sxs-lookup"><span data-stu-id="d8b81-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="d8b81-109">Kimenet: (nem, ' U) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d8b81-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="d8b81-110">Egy olyan új művelet, `op` amely egyenértékű a következővel: `op(t, u)` `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="d8b81-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d8b81-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="d8b81-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d8b81-112">Nem</span><span class="sxs-lookup"><span data-stu-id="d8b81-112">'T</span></span>

<span data-ttu-id="d8b81-113">Az első bemeneti adat típusa egy Currie-művelethez.</span><span class="sxs-lookup"><span data-stu-id="d8b81-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="d8b81-114">' U</span><span class="sxs-lookup"><span data-stu-id="d8b81-114">'U</span></span>

<span data-ttu-id="d8b81-115">A többszintű művelet második bemenetének típusa.</span><span class="sxs-lookup"><span data-stu-id="d8b81-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8b81-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="d8b81-116">See Also</span></span>

- [<span data-ttu-id="d8b81-117">Microsoft. Quantum. Canon. UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="d8b81-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="d8b81-118">Microsoft. Quantum. Canon. UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="d8b81-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="d8b81-119">Microsoft. Quantum. Canon. UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="d8b81-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)