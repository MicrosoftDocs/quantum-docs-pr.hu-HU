---
uid: Microsoft.Quantum.Canon.UncurriedOp
title: UncurriedOp függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: UncurriedOp
qsharp.summary: Given a function which returns operations, returns a new operation which takes both inputs as a tuple.
ms.openlocfilehash: 359c0b2a9dd56445fb39fadc6580809dd9fbf628
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715237"
---
# <a name="uncurriedop-function"></a><span data-ttu-id="29cae-102">UncurriedOp függvény</span><span class="sxs-lookup"><span data-stu-id="29cae-102">UncurriedOp function</span></span>

<span data-ttu-id="29cae-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="29cae-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="29cae-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="29cae-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="29cae-105">Egy olyan függvény, amely egy műveletet ad vissza, egy új műveletet ad vissza, amely mindkét bemenetet rekordként veszi át.</span><span class="sxs-lookup"><span data-stu-id="29cae-105">Given a function which returns operations, returns a new operation which takes both inputs as a tuple.</span></span>

```qsharp
function UncurriedOp<'T, 'U> (curriedOp : ('T -> ('U => Unit))) : (('T, 'U) => Unit)
```


## <a name="input"></a><span data-ttu-id="29cae-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="29cae-106">Input</span></span>

### <a name="curriedop--t---u--unit"></a><span data-ttu-id="29cae-107">curriedOp: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="29cae-107">curriedOp : 'T -> 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="29cae-108">Egy függvény, amely visszaadja A műveleteket.</span><span class="sxs-lookup"><span data-stu-id="29cae-108">A function which returns operations.</span></span>



## <a name="output--tu--unit"></a><span data-ttu-id="29cae-109">Kimenet: (nem, ' U) => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="29cae-109">Output : ('T,'U) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="29cae-110">Egy olyan új művelet, `op` amely egyenértékű a következővel: `op(t, u)` `(curriedOp(t))(u)` .</span><span class="sxs-lookup"><span data-stu-id="29cae-110">A new operation `op` such that `op(t, u)` is equivalent to `(curriedOp(t))(u)`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="29cae-111">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="29cae-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="29cae-112">Nem</span><span class="sxs-lookup"><span data-stu-id="29cae-112">'T</span></span>

<span data-ttu-id="29cae-113">Az első bemeneti adat típusa egy Currie-művelethez.</span><span class="sxs-lookup"><span data-stu-id="29cae-113">The type of the first input to a curried operation.</span></span>
### <a name="u"></a><span data-ttu-id="29cae-114">' U</span><span class="sxs-lookup"><span data-stu-id="29cae-114">'U</span></span>

<span data-ttu-id="29cae-115">A többszintű művelet második bemenetének típusa.</span><span class="sxs-lookup"><span data-stu-id="29cae-115">The type of the second input to a curried operation.</span></span>

## <a name="see-also"></a><span data-ttu-id="29cae-116">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="29cae-116">See Also</span></span>

- [<span data-ttu-id="29cae-117">Microsoft. Quantum. Canon. UncurriedOpC</span><span class="sxs-lookup"><span data-stu-id="29cae-117">Microsoft.Quantum.Canon.UncurriedOpC</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpC)
- [<span data-ttu-id="29cae-118">Microsoft. Quantum. Canon. UncurriedOpA</span><span class="sxs-lookup"><span data-stu-id="29cae-118">Microsoft.Quantum.Canon.UncurriedOpA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpA)
- [<span data-ttu-id="29cae-119">Microsoft. Quantum. Canon. UncurriedOpCA</span><span class="sxs-lookup"><span data-stu-id="29cae-119">Microsoft.Quantum.Canon.UncurriedOpCA</span></span>](xref:Microsoft.Quantum.Canon.UncurriedOpCA)