---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: f3c51410fb7c091385b64a1c4c99b3972d5055b1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715685"
---
# <a name="operationpowc-function"></a><span data-ttu-id="f0e2d-102">OperationPowC függvény</span><span class="sxs-lookup"><span data-stu-id="f0e2d-102">OperationPowC function</span></span>

<span data-ttu-id="f0e2d-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f0e2d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f0e2d-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f0e2d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f0e2d-105">Kivált egy műveletet egy hatványra.</span><span class="sxs-lookup"><span data-stu-id="f0e2d-105">Raises an operation to a power.</span></span>
<span data-ttu-id="f0e2d-106">A módosító `C` azt jelzi, hogy a művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="f0e2d-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="f0e2d-107">Ez azt jelenti, hogy egy $U $ kaput jelképező művelet miatt egy új műveletet ad vissza $U ^ m $ a Power $m $-hoz.</span><span class="sxs-lookup"><span data-stu-id="f0e2d-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="f0e2d-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f0e2d-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="f0e2d-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="f0e2d-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="f0e2d-110">A megismételni kívánt kaput jelző művelet $U $.</span><span class="sxs-lookup"><span data-stu-id="f0e2d-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="f0e2d-111">teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f0e2d-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f0e2d-112">Ennyi alkalommal kell megismételni a $U $ értéket.</span><span class="sxs-lookup"><span data-stu-id="f0e2d-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl"></a><span data-ttu-id="f0e2d-113">Kimenet: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) CTL</span><span class="sxs-lookup"><span data-stu-id="f0e2d-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="f0e2d-114">Egy új művelet, amely a $U ^ m $ értéket jelképezi, ahol $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="f0e2d-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f0e2d-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="f0e2d-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f0e2d-116">Nem</span><span class="sxs-lookup"><span data-stu-id="f0e2d-116">'T</span></span>

<span data-ttu-id="f0e2d-117">A bekapcsolni kívánt művelet típusa.</span><span class="sxs-lookup"><span data-stu-id="f0e2d-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="f0e2d-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="f0e2d-118">See Also</span></span>

- [<span data-ttu-id="f0e2d-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="f0e2d-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)