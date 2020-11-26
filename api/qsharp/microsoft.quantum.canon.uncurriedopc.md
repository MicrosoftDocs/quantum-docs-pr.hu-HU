---
uid: Microsoft.Quantum.Canon.UncurriedOpC
title: UncurriedOpC függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOpC
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple. The modifier `C` indicates that the operations are controllable.
ms.openlocfilehash: 35be5425fcd76eae9e0a6fde6a689a5db00da52f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204589"
---
# <a name="uncurriedopc-function"></a><span data-ttu-id="3b279-102">UncurriedOpC függvény</span><span class="sxs-lookup"><span data-stu-id="3b279-102">UncurriedOpC function</span></span>

<span data-ttu-id="3b279-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3b279-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3b279-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3b279-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3b279-105">Egy olyan függvény, amely egy műveletet ad vissza, egy új műveletet ad vissza, amely mindkét bemenetet rekordként veszi át.</span><span class="sxs-lookup"><span data-stu-id="3b279-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>
<span data-ttu-id="3b279-106">A módosító `C` azt jelzi, hogy a műveletek ellenőrizhetők.</span><span class="sxs-lookup"><span data-stu-id="3b279-106">The modifier `C` indicates that the operations are controllable.</span></span>

```qsharp
function UncurriedOpC<'T, 'U> (curriedOp : ('T -> ('U => Unit is Ctl))) : (('T, 'U) => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="3b279-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3b279-107">Input</span></span>

### <a name="curriedop--t---u--unit--is-ctl"></a><span data-ttu-id="3b279-108">curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="3b279-108">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="3b279-109">Egy függvény, amely visszaadja A műveleteket.</span><span class="sxs-lookup"><span data-stu-id="3b279-109">A function which returns operations.</span></span>



## <a name="output--tu--unit--is-ctl"></a><span data-ttu-id="3b279-110">Kimenet: ('T, ' U) => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="3b279-110">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="3b279-111">Egy olyan új művelet, `op` amely egyenértékű a következővel: `op(t, u)` `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="3b279-111">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3b279-112">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="3b279-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3b279-113">Nem</span><span class="sxs-lookup"><span data-stu-id="3b279-113">'T</span></span>

<span data-ttu-id="3b279-114">Egy Currie-függvény első argumentumának típusa.</span><span class="sxs-lookup"><span data-stu-id="3b279-114">The type of the first argument of a curried function.</span></span>
### <a name="u"></a><span data-ttu-id="3b279-115">' U</span><span class="sxs-lookup"><span data-stu-id="3b279-115">'U</span></span>

<span data-ttu-id="3b279-116">Egy Currie-függvény második argumentumának típusa.</span><span class="sxs-lookup"><span data-stu-id="3b279-116">The type of the second argument of a curried function.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b279-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="3b279-117">See Also</span></span>

- [<span data-ttu-id="3b279-118">Microsoft. Quantum. Canon. UncurriedOp</span><span class="sxs-lookup"><span data-stu-id="3b279-118">Microsoft.Quantum.Canon.UncurriedOp</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOp)