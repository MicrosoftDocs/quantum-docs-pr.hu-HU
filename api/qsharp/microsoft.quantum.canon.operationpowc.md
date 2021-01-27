---
uid: Microsoft.Quantum.Canon.OperationPowC
title: OperationPowC függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowC
qsharp.summary: >-
  Raises an operation to a power. The modifier `C` indicates that the operation is controllable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 05b0d5b286e16c308d8c3df8fb8fa1ac8c9868ca
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852351"
---
# <a name="operationpowc-function"></a><span data-ttu-id="1b5ca-102">OperationPowC függvény</span><span class="sxs-lookup"><span data-stu-id="1b5ca-102">OperationPowC function</span></span>

<span data-ttu-id="1b5ca-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1b5ca-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1b5ca-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b5ca-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1b5ca-105">Kivált egy műveletet egy hatványra.</span><span class="sxs-lookup"><span data-stu-id="1b5ca-105">Raises an operation to a power.</span></span>
<span data-ttu-id="1b5ca-106">A módosító `C` azt jelzi, hogy a művelet ellenőrizhető.</span><span class="sxs-lookup"><span data-stu-id="1b5ca-106">The modifier `C` indicates that the operation is controllable.</span></span>

<span data-ttu-id="1b5ca-107">Ez azt jelenti, hogy egy $U $ kaput jelképező művelet miatt egy új műveletet ad vissza $U ^ m $ a Power $m $-hoz.</span><span class="sxs-lookup"><span data-stu-id="1b5ca-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowC<'T> (op : ('T => Unit is Ctl), power : Int) : ('T => Unit is Ctl)
```


## <a name="input"></a><span data-ttu-id="1b5ca-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1b5ca-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="1b5ca-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="1b5ca-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="1b5ca-110">A megismételni kívánt kaput jelző művelet $U $.</span><span class="sxs-lookup"><span data-stu-id="1b5ca-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="1b5ca-111">teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1b5ca-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1b5ca-112">Ennyi alkalommal kell megismételni a $U $ értéket.</span><span class="sxs-lookup"><span data-stu-id="1b5ca-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-ctl"></a><span data-ttu-id="1b5ca-113">Kimenet: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  CTL</span><span class="sxs-lookup"><span data-stu-id="1b5ca-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="1b5ca-114">Egy új művelet, amely a $U ^ m $ értéket jelképezi, ahol $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="1b5ca-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1b5ca-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="1b5ca-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1b5ca-116">Nem</span><span class="sxs-lookup"><span data-stu-id="1b5ca-116">'T</span></span>

<span data-ttu-id="1b5ca-117">A bekapcsolni kívánt művelet típusa.</span><span class="sxs-lookup"><span data-stu-id="1b5ca-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b5ca-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="1b5ca-118">See Also</span></span>

- [<span data-ttu-id="1b5ca-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="1b5ca-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)