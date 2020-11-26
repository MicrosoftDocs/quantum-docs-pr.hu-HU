---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 35dc76a06fd4e8c819b785fd4c588f108c918326
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205779"
---
# <a name="operationpowa-function"></a><span data-ttu-id="74535-102">OperationPowA függvény</span><span class="sxs-lookup"><span data-stu-id="74535-102">OperationPowA function</span></span>

<span data-ttu-id="74535-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="74535-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="74535-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="74535-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="74535-105">Kivált egy műveletet egy hatványra.</span><span class="sxs-lookup"><span data-stu-id="74535-105">Raises an operation to a power.</span></span>
<span data-ttu-id="74535-106">A módosító `A` azt jelzi, hogy a művelet adjointable.</span><span class="sxs-lookup"><span data-stu-id="74535-106">The modifier `A` indicates that the operation is adjointable.</span></span>

<span data-ttu-id="74535-107">Ez azt jelenti, hogy egy $U $ kaput jelképező művelet miatt egy új műveletet ad vissza $U ^ m $ a Power $m $-hoz.</span><span class="sxs-lookup"><span data-stu-id="74535-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="74535-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="74535-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="74535-109">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="74535-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="74535-110">A megismételni kívánt kaput jelző művelet $U $.</span><span class="sxs-lookup"><span data-stu-id="74535-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="74535-111">teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="74535-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="74535-112">Ennyi alkalommal kell megismételni a $U $ értéket.</span><span class="sxs-lookup"><span data-stu-id="74535-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit--is-adj"></a><span data-ttu-id="74535-113">Kimenet: nem => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="74535-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="74535-114">Egy új művelet, amely a $U ^ m $ értéket jelképezi, ahol $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="74535-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="74535-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="74535-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="74535-116">Nem</span><span class="sxs-lookup"><span data-stu-id="74535-116">'T</span></span>

<span data-ttu-id="74535-117">A bekapcsolni kívánt művelet típusa.</span><span class="sxs-lookup"><span data-stu-id="74535-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="74535-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="74535-118">See Also</span></span>

- [<span data-ttu-id="74535-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="74535-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)