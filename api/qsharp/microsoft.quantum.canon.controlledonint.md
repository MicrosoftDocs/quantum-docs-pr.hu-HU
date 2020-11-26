---
uid: Microsoft.Quantum.Canon.ControlledOnInt
title: ControlledOnInt függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnInt
qsharp.summary: Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: 3cc5c00d9c7295106901149e06571ef1963d1323
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207258"
---
# <a name="controlledonint-function"></a><span data-ttu-id="9741a-102">ControlledOnInt függvény</span><span class="sxs-lookup"><span data-stu-id="9741a-102">ControlledOnInt function</span></span>

<span data-ttu-id="9741a-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9741a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9741a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9741a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9741a-105">Egy olyan egységes operátort ad vissza, amely egy Oracle-t alkalmaz a cél-tételjegyzékben, ha a vezérlő regisztrálása állapot egy megadott pozitív egész számnak felel meg.</span><span class="sxs-lookup"><span data-stu-id="9741a-105">Returns a unitary operator that applies an oracle on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
function ControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="9741a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9741a-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="9741a-107">numberState: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9741a-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9741a-108">Pozitív egész szám.</span><span class="sxs-lookup"><span data-stu-id="9741a-108">Positive integer.</span></span>


### <a name="oracle--t--unit--is-adj--ctl"></a><span data-ttu-id="9741a-109">Oracle: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="9741a-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9741a-110">Egységes operátor.</span><span class="sxs-lookup"><span data-stu-id="9741a-110">Unitary operator.</span></span>



## <a name="output--qubitt--unit--is-adj--ctl"></a><span data-ttu-id="9741a-111">Kimenet: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[], 't) => [egység](xref:microsoft.quantum.lang-ref.unit)  : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="9741a-111">Output : ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="9741a-112">Egy egységes operátor, amely a `oracle` cél-regisztrációra vonatkozik, ha a vezérlő regisztrálása állapot megfelel a szám állapotnak `numberState` .</span><span class="sxs-lookup"><span data-stu-id="9741a-112">A unitary operator that applies `oracle` on the target register if the control register state corresponds to the number state `numberState`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9741a-113">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="9741a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9741a-114">Nem</span><span class="sxs-lookup"><span data-stu-id="9741a-114">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="9741a-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="9741a-115">Remarks</span></span>

<span data-ttu-id="9741a-116">A értéke `numberState` kis endian kódolással értelmezhető.</span><span class="sxs-lookup"><span data-stu-id="9741a-116">The value of `numberState` is interpreted using a little-endian encoding.</span></span>