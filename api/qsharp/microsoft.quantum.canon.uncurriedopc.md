---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: f3e5ecf3f7df0393dfbb948f064c27505f04cfcf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715209"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="529da-102">UncurriedOpC függvény</span><span class="sxs-lookup"><span data-stu-id="529da-102">UncurriedOpC function</span></span>

<span data-ttu-id="529da-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="529da-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="529da-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="529da-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="529da-105">Egy olyan függvény, amely egy műveletet ad vissza, egy új műveletet ad vissza, amely mindkét bemenetet rekordként veszi át.</span><span class="sxs-lookup"><span data-stu-id="529da-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="529da-106">A módosító `C` azt jelzi, hogy a műveletek ellenőrizhetők.</span><span class="sxs-lookup"><span data-stu-id="529da-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="529da-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="529da-107">Input</span></span>

### <a name="curriedop--t---u--unit-ctl"></a><span data-ttu-id="529da-108">curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="529da-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="529da-109">Egy függvény, amely visszaadja A műveleteket.</span><span class="sxs-lookup"><span data-stu-id="529da-109">A function which returns operations.</span></span>



## <a name="output--tu--unit-ctl"></a><span data-ttu-id="529da-110">Kimenet: (nem, ' U) => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="529da-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="529da-111">Egy olyan új művelet, `op` amely egyenértékű a következővel: `op(t, u)` `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="529da-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="529da-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="529da-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="529da-113">Nem</span><span class="sxs-lookup"><span data-stu-id="529da-113">'T</span></span>

<span data-ttu-id="529da-114">Egy Currie-függvény első argumentumának típusa.</span><span class="sxs-lookup"><span data-stu-id="529da-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="529da-115">' U</span><span class="sxs-lookup"><span data-stu-id="529da-115">'U</span></span>

<span data-ttu-id="529da-116">Egy Currie-függvény második argumentumának típusa.</span><span class="sxs-lookup"><span data-stu-id="529da-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="529da-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="529da-117">See Also</span></span>

- [<span data-ttu-id="529da-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="529da-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)