---
uid: Microsoft.Quantum.Canon.UncurriedOpA
title: UncurriedOpA függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `A` indicates that the operations are adjointable.
ms.openlocfilehash: e535d017d2665ddb76e5f422e18b8656c73171c6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204623"
---
# <a name="uncurriedopa-function"></a><span data-ttu-id="39979-102">UncurriedOpA függvény</span><span class="sxs-lookup"><span data-stu-id="39979-102">UncurriedOpA function</span></span>

<span data-ttu-id="39979-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="39979-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="39979-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="39979-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="39979-105">Egy olyan függvény, amely egy műveletet ad vissza, egy új műveletet ad vissza, amely mindkét bemenetet rekordként veszi át.</span><span class="sxs-lookup"><span data-stu-id="39979-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="39979-106">A módosító `A` azt jelzi, hogy a műveletek adjointable.</span><span class="sxs-lookup"><span data-stu-id="39979-106">The modifier `A` indicates that the operations are adjointable.</span></span>

```qsharp
function UncurriedOpA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Adj))) : (('T, 'U) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="39979-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="39979-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj"></a><span data-ttu-id="39979-108">curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39979-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="39979-109">Egy függvény, amely visszaadja A műveleteket.</span><span class="sxs-lookup"><span data-stu-id="39979-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj"></a><span data-ttu-id="39979-110">Kimenet: (nem, ' U) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="39979-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="39979-111">Egy olyan új művelet, `op` amely egyenértékű a következővel: `op(t, u)` `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="39979-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="39979-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="39979-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="39979-113">Nem</span><span class="sxs-lookup"><span data-stu-id="39979-113">'T</span></span>

<span data-ttu-id="39979-114">Egy Currie-függvény első argumentumának típusa.</span><span class="sxs-lookup"><span data-stu-id="39979-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="39979-115">' U</span><span class="sxs-lookup"><span data-stu-id="39979-115">'U</span></span>

<span data-ttu-id="39979-116">Egy Currie-függvény második argumentumának típusa.</span><span class="sxs-lookup"><span data-stu-id="39979-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="39979-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="39979-117">See Also</span></span>

- [<span data-ttu-id="39979-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="39979-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)