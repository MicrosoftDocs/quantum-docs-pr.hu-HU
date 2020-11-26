---
uid: Microsoft.Quantum.Canon.OperationPow
title: OperationPow függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPow
qsharp.summary: >-
  Raises an operation to a power.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 808001200d276ca21cc5a70140d5d84d96da3496
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205813"
---
# <a name="operationpow-function"></a><span data-ttu-id="80579-102">OperationPow függvény</span><span class="sxs-lookup"><span data-stu-id="80579-102">OperationPow function</span></span>

<span data-ttu-id="80579-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="80579-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="80579-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="80579-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="80579-105">Kivált egy műveletet egy hatványra.</span><span class="sxs-lookup"><span data-stu-id="80579-105">Raises an operation to a power.</span></span>

<span data-ttu-id="80579-106">Ez azt jelenti, hogy egy $U $ kaput jelképező művelet miatt egy új műveletet ad vissza $U ^ m $ a Power $m $-hoz.</span><span class="sxs-lookup"><span data-stu-id="80579-106">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPow<'T> (op : ('T => Unit), power : Int) : ('T => Unit)
```


## <a name="input"></a><span data-ttu-id="80579-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="80579-107">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="80579-108">op: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80579-108">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="80579-109">A megismételni kívánt kaput jelző művelet $U $.</span><span class="sxs-lookup"><span data-stu-id="80579-109">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="80579-110">teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="80579-110">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="80579-111">Ennyi alkalommal kell megismételni a $U $ értéket.</span><span class="sxs-lookup"><span data-stu-id="80579-111">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit"></a><span data-ttu-id="80579-112">Kimenet: nem => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="80579-112">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="80579-113">Egy új művelet, amely a $U ^ m $ értéket jelképezi, ahol $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="80579-113">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="80579-114">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="80579-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="80579-115">Nem</span><span class="sxs-lookup"><span data-stu-id="80579-115">'T</span></span>

<span data-ttu-id="80579-116">A bekapcsolni kívánt művelet típusa.</span><span class="sxs-lookup"><span data-stu-id="80579-116">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="80579-117">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="80579-117">See Also</span></span>

- [<span data-ttu-id="80579-118">Microsoft. Quantum. Canon. OperationPowC</span><span class="sxs-lookup"><span data-stu-id="80579-118">Microsoft.Quantum.Canon.OperationPowC</span></span>](xref:Microsoft.Quantum.Canon.OperationPowC)
- [<span data-ttu-id="80579-119">Microsoft. Quantum. Canon. OperationPowA</span><span class="sxs-lookup"><span data-stu-id="80579-119">Microsoft.Quantum.Canon.OperationPowA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowA)
- [<span data-ttu-id="80579-120">Microsoft. Quantum. Canon. OperationPowCA</span><span class="sxs-lookup"><span data-stu-id="80579-120">Microsoft.Quantum.Canon.OperationPowCA</span></span>](xref:Microsoft.Quantum.Canon.OperationPowCA)