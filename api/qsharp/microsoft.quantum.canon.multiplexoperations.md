---
uid: Microsoft.Quantum.Canon.MultiplexOperations
title: MultiplexOperations művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperations
qsharp.summary: >-
  Applies an array of operations controlled by an array of number states.

  That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.

  $U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: ad66b39fcfacbe5231ec3b9ba96989d6d5d449c1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206102"
---
# <a name="multiplexoperations-operation"></a><span data-ttu-id="d6f4c-102">MultiplexOperations művelet</span><span class="sxs-lookup"><span data-stu-id="d6f4c-102">MultiplexOperations operation</span></span>

<span data-ttu-id="d6f4c-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d6f4c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d6f4c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d6f4c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d6f4c-105">A több állapotú tömb által vezérelt műveletek tömbjét alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="d6f4c-105">Applies an array of operations controlled by an array of number states.</span></span>

<span data-ttu-id="d6f4c-106">Ez azt is alkalmazza, hogy a szorzás által vezérelt egységes művelet $U $, amely egy egységes $V _j $-t alkalmaz, ha $n $-qubit számú állapotot ($ \ket{j} $) szabályozza.</span><span class="sxs-lookup"><span data-stu-id="d6f4c-106">That is, applies Multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by $n$-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="d6f4c-107">$U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="d6f4c-107">$U = \sum^{2^n-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperations<'T> (unitaries : ('T => Unit is Adj + Ctl)[], index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d6f4c-108">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d6f4c-108">Input</span></span>

### <a name="unitaries--t--unit--is-adj--ctl"></a><span data-ttu-id="d6f4c-109">unitaries: 'T => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL []</span><span class="sxs-lookup"><span data-stu-id="d6f4c-109">unitaries : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl[]</span></span>

<span data-ttu-id="d6f4c-110">Akár $2 ^ n $ egységes műveletből álló tömb.</span><span class="sxs-lookup"><span data-stu-id="d6f4c-110">Array of up to $2^n$ unitary operations.</span></span> <span data-ttu-id="d6f4c-111">A $j $ th műveletet a (\ket{j} $) számú, Little-endian formátumban kódolt számú állapot indexeli.</span><span class="sxs-lookup"><span data-stu-id="d6f4c-111">The $j$th operation is indexed by the number state $\ket{j}$ encoded in little-endian format.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="d6f4c-112">index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d6f4c-112">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d6f4c-113">$n $-qubit-vezérlő regisztrálása, amely kis endian formátumban kódolja a szám állapotot $ \ket{j} $ értékre.</span><span class="sxs-lookup"><span data-stu-id="d6f4c-113">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="d6f4c-114">cél: nem</span><span class="sxs-lookup"><span data-stu-id="d6f4c-114">target : 'T</span></span>

<span data-ttu-id="d6f4c-115">Az általános qubit regisztrálja, hogy $V _j $ működik.</span><span class="sxs-lookup"><span data-stu-id="d6f4c-115">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d6f4c-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d6f4c-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d6f4c-117">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="d6f4c-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d6f4c-118">Nem</span><span class="sxs-lookup"><span data-stu-id="d6f4c-118">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="d6f4c-119">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d6f4c-119">Remarks</span></span>

<span data-ttu-id="d6f4c-120">`coefficients` Ha kevesebb, mint $2 ^ n $ érték van megadva, akkor az azonosító elemek kitöltése megtörténik.</span><span class="sxs-lookup"><span data-stu-id="d6f4c-120">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="d6f4c-121">Ez a megvalósítás $n-$1 kiegészítő qubits használ.</span><span class="sxs-lookup"><span data-stu-id="d6f4c-121">This implementation uses $n - 1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="d6f4c-122">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="d6f4c-122">References</span></span>

- <span data-ttu-id="d6f4c-123">Az első kvantum-szimuláció felé a kvantum-gyorsulás Andrew M. Childs, Dmitrij Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span><span class="sxs-lookup"><span data-stu-id="d6f4c-123">Toward the first quantum simulation with quantum speedup Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su https://arxiv.org/abs/1711.10980</span></span>