---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 910d8a3006a2f217888b791e479e10f9f1a6965e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840042"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="ec407-102">UncurriedOpCA függvény</span><span class="sxs-lookup"><span data-stu-id="ec407-102">UncurriedOpCA function</span></span>

<span data-ttu-id="ec407-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ec407-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ec407-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ec407-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ec407-105">Egy olyan függvény, amely egy műveletet ad vissza, egy új műveletet ad vissza, amely mindkét bemenetet rekordként veszi át.</span><span class="sxs-lookup"><span data-stu-id="ec407-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="ec407-106">A módosító `CA` azt jelzi, hogy a műveletek ellenőrizhetők és adjointable.</span><span class="sxs-lookup"><span data-stu-id="ec407-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="ec407-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ec407-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj--ctl"></a><span data-ttu-id="ec407-108">curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="ec407-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ec407-109">Egy függvény, amely visszaadja A műveleteket.</span><span class="sxs-lookup"><span data-stu-id="ec407-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj--ctl"></a><span data-ttu-id="ec407-110">Kimenet: ('T, ' U) => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="ec407-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ec407-111">Egy olyan új művelet, `op` amely egyenértékű a következővel: `op(t, u)` `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="ec407-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ec407-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="ec407-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ec407-113">Nem</span><span class="sxs-lookup"><span data-stu-id="ec407-113">'T</span></span>

<span data-ttu-id="ec407-114">Egy Currie-függvény első argumentumának típusa.</span><span class="sxs-lookup"><span data-stu-id="ec407-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="ec407-115">' U</span><span class="sxs-lookup"><span data-stu-id="ec407-115">'U</span></span>

<span data-ttu-id="ec407-116">Egy Currie-függvény második argumentumának típusa.</span><span class="sxs-lookup"><span data-stu-id="ec407-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="ec407-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="ec407-117">See Also</span></span>

- [<span data-ttu-id="ec407-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="ec407-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)