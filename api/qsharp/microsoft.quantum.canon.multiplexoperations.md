---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: MultiplexOperations művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 1cf483bb0d3b7cc43d271b65a2363fab95ff0f3b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852532"
---
# <a name="multiplexoperations-operation"></a><span data-ttu-id="2dfe8-102">MultiplexOperations művelet</span><span class="sxs-lookup"><span data-stu-id="2dfe8-102">MultiplexOperations operation</span></span>

<span data-ttu-id="2dfe8-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2dfe8-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2dfe8-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2dfe8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2dfe8-105">A több állapotú tömb által vezérelt műveletek tömbjét alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-105">Applies an array of operations controlled by an array of number states.</span></span>

<span data-ttu-id="2dfe8-106">Ez azt is alkalmazza, hogy a szorzás által vezérelt egységes művelet $U $, amely egy egységes $V _j $-t alkalmaz, ha $n $-qubit számú állapotot ($ \ket{j} $) szabályozza.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-106">That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="2dfe8-107">$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-107">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2dfe8-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2dfe8-108">Input</span></span>

### <a name="unitaries--t--unit--is-adj--ctl"></a><span data-ttu-id="2dfe8-109">unitaries: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL []</span><span class="sxs-lookup"><span data-stu-id="2dfe8-109">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="2dfe8-110">Akár $2 ^ n $ egységes műveletből álló tömb.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-110">Array of up to $2^n$ unitary operations.</span></span> <span data-ttu-id="2dfe8-111">A $j $ th műveletet a (\ket{j} $) számú, Little-endian formátumban kódolt számú állapot indexeli.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-111">The $j$th operation is indexed by the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="2dfe8-112">index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="2dfe8-112">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="2dfe8-113">$n $-qubit-vezérlő regisztrálása, amely kis endian formátumban kódolja a szám állapotot $ \ket{j} $ értékre.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-113">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="2dfe8-114">cél: nem</span><span class="sxs-lookup"><span data-stu-id="2dfe8-114">target : 'T</span></span>

<span data-ttu-id="2dfe8-115">Az általános qubit regisztrálja, hogy $V _j $ működik.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-115">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2dfe8-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2dfe8-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2dfe8-117">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="2dfe8-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2dfe8-118">Nem</span><span class="sxs-lookup"><span data-stu-id="2dfe8-118">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="2dfe8-119">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="2dfe8-119">Remarks</span></span>

<span data-ttu-id="2dfe8-120">`coefficients` Ha kevesebb, mint $2 ^ n $ érték van megadva, akkor az azonosító elemek kitöltése megtörténik.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-120">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="2dfe8-121">Ez a megvalósítás $n-$1 kiegészítő qubits használ.</span><span class="sxs-lookup"><span data-stu-id="2dfe8-121">This implementation uses $n - 1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="2dfe8-122">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="2dfe8-122">References</span></span>

- <span data-ttu-id="2dfe8-123">Az első kvantum-szimuláció felé a kvantum-gyorsulás Andrew M. Childs, Dmitrij Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span><span class="sxs-lookup"><span data-stu-id="2dfe8-123">Toward the first quantum simulation with quantum speedup Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span></span>