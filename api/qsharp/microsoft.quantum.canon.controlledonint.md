---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 4c48f3257f91fc50040d02cae7c2f7bdf87ea7c5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716413"
---
# <a name="controlledonint-function"></a><span data-ttu-id="c9b88-102">ControlledOnInt függvény</span><span class="sxs-lookup"><span data-stu-id="c9b88-102">ControlledOnInt function</span></span>

<span data-ttu-id="c9b88-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c9b88-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c9b88-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c9b88-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c9b88-105">Egy olyan egységes operátort ad vissza, amely egy Oracle-t alkalmaz a cél-tételjegyzékben, ha a vezérlő regisztrálása állapot egy megadott pozitív egész számnak felel meg.</span><span class="sxs-lookup"><span data-stu-id="c9b88-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="c9b88-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="c9b88-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="c9b88-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c9b88-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c9b88-108">Pozitív egész szám.</span><span class="sxs-lookup"><span data-stu-id="c9b88-108">Positive integer.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="c9b88-109">Oracle: 'T => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="c9b88-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c9b88-110">Egységes operátor.</span><span class="sxs-lookup"><span data-stu-id="c9b88-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit-adj--ctl"></a><span data-ttu-id="c9b88-111">Kimenet: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[], nem) => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="c9b88-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c9b88-112">Egy egységes operátor, amely a `oracle` cél-regisztrációra vonatkozik, ha a vezérlő regisztrálása állapot megfelel a szám állapotnak `numberState` .</span><span class="sxs-lookup"><span data-stu-id="c9b88-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c9b88-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="c9b88-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c9b88-114">Nem</span><span class="sxs-lookup"><span data-stu-id="c9b88-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="c9b88-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="c9b88-115">Remarks</span></span>

<span data-ttu-id="c9b88-116">A értéke `numberState` kis endian kódolással értelmezhető.</span><span class="sxs-lookup"><span data-stu-id="c9b88-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>