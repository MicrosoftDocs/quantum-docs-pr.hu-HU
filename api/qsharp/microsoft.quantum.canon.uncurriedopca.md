---
uid: Microsoft.Quantum.Canon.UncurriedOpCA
title: UncurriedOpCA függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpCA
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `CA` indicates that the operations are controllable and adjointable.
ms.openlocfilehash: 45526c0202e417213aab3fe7819827588e794e23
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216387"
---
# <a name="uncurriedopca-function"></a><span data-ttu-id="d8953-102">UncurriedOpCA függvény</span><span class="sxs-lookup"><span data-stu-id="d8953-102">UncurriedOpCA function</span></span>

<span data-ttu-id="d8953-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d8953-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d8953-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d8953-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d8953-105">Egy olyan függvény, amely egy műveletet ad vissza, egy új műveletet ad vissza, amely mindkét bemenetet rekordként veszi át.</span><span class="sxs-lookup"><span data-stu-id="d8953-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="d8953-106">A módosító `CA` azt jelzi, hogy a műveletek ellenőrizhetők és adjointable.</span><span class="sxs-lookup"><span data-stu-id="d8953-106">The modifier `CA` indicates that the operations are controllable and adjointable.</span></span>

```qsharp
function UncurriedOpCA<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl + Adj))) : (('T, 'U) => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="d8953-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d8953-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-adj--ctl"></a><span data-ttu-id="d8953-108">curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="d8953-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d8953-109">Egy függvény, amely visszaadja A műveleteket.</span><span class="sxs-lookup"><span data-stu-id="d8953-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-adj--ctl"></a><span data-ttu-id="d8953-110">Kimenet: ('T, ' U) => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="d8953-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d8953-111">Egy olyan új művelet, `op` amely egyenértékű a következővel: `op(t, u)` `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="d8953-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d8953-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="d8953-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d8953-113">Nem</span><span class="sxs-lookup"><span data-stu-id="d8953-113">'T</span></span>

<span data-ttu-id="d8953-114">Egy Currie-függvény első argumentumának típusa.</span><span class="sxs-lookup"><span data-stu-id="d8953-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="d8953-115">' U</span><span class="sxs-lookup"><span data-stu-id="d8953-115">'U</span></span>

<span data-ttu-id="d8953-116">Egy Currie-függvény második argumentumának típusa.</span><span class="sxs-lookup"><span data-stu-id="d8953-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="d8953-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="d8953-117">See Also</span></span>

- [<span data-ttu-id="d8953-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="d8953-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)