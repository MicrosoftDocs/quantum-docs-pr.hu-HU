---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: cad508f166d4af805cb98cd21a0260d9babb6a4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204640"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="7a28f-102">UncurriedOp függvény</span><span class="sxs-lookup"><span data-stu-id="7a28f-102">UncurriedOp function</span></span>

<span data-ttu-id="7a28f-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7a28f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7a28f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7a28f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7a28f-105">Egy olyan függvény, amely egy műveletet ad vissza, egy új műveletet ad vissza, amely mindkét bemenetet rekordként veszi át.</span><span class="sxs-lookup"><span data-stu-id="7a28f-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="7a28f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7a28f-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="7a28f-107">curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a28f-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7a28f-108">Egy függvény, amely visszaadja A műveleteket.</span><span class="sxs-lookup"><span data-stu-id="7a28f-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="7a28f-109">Kimenet: (nem, ' U) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7a28f-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7a28f-110">Egy olyan új művelet, `op` amely egyenértékű a következővel: `op(t, u)` `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="7a28f-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7a28f-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="7a28f-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7a28f-112">Nem</span><span class="sxs-lookup"><span data-stu-id="7a28f-112">'T</span></span>

<span data-ttu-id="7a28f-113">Az első bemeneti adat típusa egy Currie-művelethez.</span><span class="sxs-lookup"><span data-stu-id="7a28f-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="7a28f-114">' U</span><span class="sxs-lookup"><span data-stu-id="7a28f-114">'U</span></span>

<span data-ttu-id="7a28f-115">A többszintű művelet második bemenetének típusa.</span><span class="sxs-lookup"><span data-stu-id="7a28f-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a28f-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="7a28f-116">See Also</span></span>

- [<span data-ttu-id="7a28f-117">Microsoft. Quantum. Canon. UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="7a28f-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="7a28f-118">Microsoft. Quantum. Canon. UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="7a28f-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="7a28f-119">Microsoft. Quantum. Canon. UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="7a28f-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)