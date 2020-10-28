---
uid: Microsoft.Quantum.Canon.OperationPowA
title: OperationPowA függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: OperationPowA
qsharp.summary: >-
  Raises an operation to a power. The modifier `A` indicates that the operation is adjointable.

  That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.
ms.openlocfilehash: 66df354c6de7e48624712276882759043b78466c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715713"
---
# <a name="operationpowa-function"></a><span data-ttu-id="129f1-102">OperationPowA függvény</span><span class="sxs-lookup"><span data-stu-id="129f1-102">OperationPowA function</span></span>

<span data-ttu-id="129f1-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="129f1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="129f1-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="129f1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="129f1-105">Kivált egy műveletet egy hatványra.</span><span class="sxs-lookup"><span data-stu-id="129f1-105">Raises an operation to a power.</span></span>
<span data-ttu-id="129f1-106">A módosító `A` azt jelzi, hogy a művelet adjointable.</span><span class="sxs-lookup"><span data-stu-id="129f1-106">The modifier `A` indicates that the operation is adjointable.</span></span>

<span data-ttu-id="129f1-107">Ez azt jelenti, hogy egy $U $ kaput jelképező művelet miatt egy új műveletet ad vissza $U ^ m $ a Power $m $-hoz.</span><span class="sxs-lookup"><span data-stu-id="129f1-107">That is, given an operation representing a gate $U$, returns a new operation $U^m$ for a power $m$.</span></span>

```qsharp
function OperationPowA<'T> (op : ('T => Unit is Adj), power : Int) : ('T => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="129f1-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="129f1-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="129f1-109">op: nem =>i [egység](xref:microsoft.quantum.lang-ref.unit) – Adj</span><span class="sxs-lookup"><span data-stu-id="129f1-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="129f1-110">A megismételni kívánt kaput jelző művelet $U $.</span><span class="sxs-lookup"><span data-stu-id="129f1-110">An operation $U$ representing the gate to be repeated.</span></span>


### <a name="power--int"></a><span data-ttu-id="129f1-111">teljesítmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="129f1-111">power : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="129f1-112">Ennyi alkalommal kell megismételni a $U $ értéket.</span><span class="sxs-lookup"><span data-stu-id="129f1-112">The number of times that $U$ is to be repeated.</span></span>



## <a name="output--t--unit-adj"></a><span data-ttu-id="129f1-113">Kimenet: nem =>i [egység](xref:microsoft.quantum.lang-ref.unit) : Adj</span><span class="sxs-lookup"><span data-stu-id="129f1-113">Output : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="129f1-114">Egy új művelet, amely a $U ^ m $ értéket jelképezi, ahol $m = \texttt{Power} $.</span><span class="sxs-lookup"><span data-stu-id="129f1-114">A new operation representing $U^m$, where $m = \texttt{power}$.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="129f1-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="129f1-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="129f1-116">Nem</span><span class="sxs-lookup"><span data-stu-id="129f1-116">'T</span></span>

<span data-ttu-id="129f1-117">A bekapcsolni kívánt művelet típusa.</span><span class="sxs-lookup"><span data-stu-id="129f1-117">The type of the operation to be powered.</span></span>

## <a name="see-also"></a><span data-ttu-id="129f1-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="129f1-118">See Also</span></span>

- [<span data-ttu-id="129f1-119">Microsoft. Quantum. Canon. OperationPow</span><span class="sxs-lookup"><span data-stu-id="129f1-119">Microsoft.Quantum.Canon.OperationPow</span></span>](xref:Microsoft.Quantum.Canon.OperationPow)