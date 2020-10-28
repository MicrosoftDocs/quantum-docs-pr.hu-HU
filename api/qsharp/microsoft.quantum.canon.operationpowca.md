---
uid: Microsoft.Quantum.Canon.OperationPowCA
title: OperationPowCA függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowCA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is controllable and adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 753063452616747309e3e228ce8a702f4378c61f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715671"
---
# <a name="operationpowca-function"></a><span data-ttu-id="3610c-102">OperationPowCA függvény</span><span class="sxs-lookup"><span data-stu-id="3610c-102">OperationPowCA function</span></span>

<span data-ttu-id="3610c-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3610c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3610c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3610c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3610c-105">Kivált egy műveletet egy hatványra.</span><span class="sxs-lookup"><span data-stu-id="3610c-105">Raises an operation to a power.</span></span>
<span data-ttu-id="3610c-106">A módosító `A` azt jelzi, hogy a művelet ellenőrizhető és adjointable.</span><span class="sxs-lookup"><span data-stu-id="3610c-106">The modifier `A` indicates that the operation is controllable and adjointable.</span></span>

<span data-ttu-id="3610c-107">Ez azt jelenti, hogy egy $U $ kaput jelképező művelet miatt egy új műveletet ad vissza $U ^ m $ a Power $m $-hoz.</span><span class="sxs-lookup"><span data-stu-id="3610c-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowCA<'T> (op : ('T => Unit is Ctl + Adj), power : Int) : ('T => Unit is Ctl + Adj)
```


## <a name="input"></a><span data-ttu-id="3610c-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3610c-108">Input</span></span>

### <a name="op--t--unit-ctl--adj"></a><span data-ttu-id="3610c-109">op: nem => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj</span><span class="sxs-lookup"><span data-stu-id="3610c-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="3610c-110">A megismételni kívánt kaput jelző művelet $U $.</span><span class="sxs-lookup"><span data-stu-id="3610c-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="3610c-111">teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="3610c-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="3610c-112">Ennyi alkalommal kell megismételni a $U $ értéket.</span><span class="sxs-lookup"><span data-stu-id="3610c-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-ctl--adj"></a><span data-ttu-id="3610c-113">Kimenet: nem => [egység](xref:microsoft.quantum.lang-ref.unit) CTL + Adj</span><span class="sxs-lookup"><span data-stu-id="3610c-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + Adj</span></span>

<span data-ttu-id="3610c-114">Egy új művelet, amely a $U ^ m $ értéket jelképezi, ahol $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="3610c-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3610c-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="3610c-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3610c-116">Nem</span><span class="sxs-lookup"><span data-stu-id="3610c-116">'T</span></span>

<span data-ttu-id="3610c-117">A bekapcsolni kívánt művelet típusa.</span><span class="sxs-lookup"><span data-stu-id="3610c-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="3610c-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="3610c-118">See Also</span></span>

- [<span data-ttu-id="3610c-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="3610c-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)