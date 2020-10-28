---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 6a0f2e1b345d0ba3ac5c779c5dc2bfffaf659a0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715208"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="b27a6-102">UncurriedOpCA függvény</span><span class="sxs-lookup"><span data-stu-id="b27a6-102">UncurriedOpCA function</span></span>

<span data-ttu-id="b27a6-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b27a6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b27a6-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b27a6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b27a6-105">Egy olyan függvény, amely egy műveletet ad vissza, egy új műveletet ad vissza, amely mindkét bemenetet rekordként veszi át.</span><span class="sxs-lookup"><span data-stu-id="b27a6-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="b27a6-106">A módosító `CA` azt jelzi, hogy a műveletek ellenőrizhetők és adjointable.</span><span class="sxs-lookup"><span data-stu-id="b27a6-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="b27a6-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b27a6-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl--adj"></a><span data-ttu-id="b27a6-108">curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj</span><span class="sxs-lookup"><span data-stu-id="b27a6-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="b27a6-109">Egy függvény, amely visszaadja A műveleteket.</span><span class="sxs-lookup"><span data-stu-id="b27a6-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl--adj"></a><span data-ttu-id="b27a6-110">Kimenet: (nem, ' U) => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj</span><span class="sxs-lookup"><span data-stu-id="b27a6-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="b27a6-111">Egy olyan új művelet, `op` amely egyenértékű a következővel: `op(t, u)` `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="b27a6-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b27a6-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="b27a6-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b27a6-113">Nem</span><span class="sxs-lookup"><span data-stu-id="b27a6-113">'T</span></span>

<span data-ttu-id="b27a6-114">Egy Currie-függvény első argumentumának típusa.</span><span class="sxs-lookup"><span data-stu-id="b27a6-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="b27a6-115">' U</span><span class="sxs-lookup"><span data-stu-id="b27a6-115">'U</span></span>

<span data-ttu-id="b27a6-116">Egy Currie-függvény második argumentumának típusa.</span><span class="sxs-lookup"><span data-stu-id="b27a6-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="b27a6-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="b27a6-117">See Also</span></span>

- [<span data-ttu-id="b27a6-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="b27a6-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)