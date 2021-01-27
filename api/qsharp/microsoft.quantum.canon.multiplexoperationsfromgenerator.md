---
uid: Microsoft.Quantum.Canon.MultiplexOperationsFromGenerator
title: MultiplexOperationsFromGenerator művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsFromGenerator
qsharp.summary: >-
  Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: 59afa9d9a34fe74206118680940d243ed8b2496e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852496"
---
# <a name="multiplexoperationsfromgenerator-operation"></a><span data-ttu-id="4ff7c-102">MultiplexOperationsFromGenerator művelet</span><span class="sxs-lookup"><span data-stu-id="4ff7c-102">MultiplexOperationsFromGenerator operation</span></span>

<span data-ttu-id="4ff7c-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4ff7c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4ff7c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4ff7c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4ff7c-105">Egy szorzásra vezérelt, egységes műveletet alkalmaz, $U $, amely egy egységes $V _j $-t alkalmaz, ha n-qubit számú \ket{j} $ értékkel van szabályozva.</span><span class="sxs-lookup"><span data-stu-id="4ff7c-105">Applies a multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="4ff7c-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="4ff7c-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4ff7c-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4ff7c-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a><span data-ttu-id="4ff7c-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> 't => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL)</span><span class="sxs-lookup"><span data-stu-id="4ff7c-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="4ff7c-109">Egy rekord, amelyben az első elem `Int` a unitaries $N $, a második elem `(Int -> ('T => () is Adj + Ctl))` pedig egy függvény, amely egy egész $j $ értéket vesz igénybe $ [0, N-1] $ értékben, és az egységes művelet $V _j $ értéket adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="4ff7c-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="4ff7c-110">index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="4ff7c-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="4ff7c-111">$n $-qubit-vezérlő regisztrálása, amely kis endian formátumban kódolja a szám állapotot $ \ket{j} $ értékre.</span><span class="sxs-lookup"><span data-stu-id="4ff7c-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="4ff7c-112">cél: nem</span><span class="sxs-lookup"><span data-stu-id="4ff7c-112">target : 'T</span></span>

<span data-ttu-id="4ff7c-113">Az általános qubit regisztrálja, hogy $V _j $ működik.</span><span class="sxs-lookup"><span data-stu-id="4ff7c-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4ff7c-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4ff7c-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4ff7c-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="4ff7c-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4ff7c-116">Nem</span><span class="sxs-lookup"><span data-stu-id="4ff7c-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="4ff7c-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="4ff7c-117">Remarks</span></span>

<span data-ttu-id="4ff7c-118">`coefficients` Ha kevesebb, mint $2 ^ n $ érték van megadva, akkor az azonosító elemek kitöltése megtörténik.</span><span class="sxs-lookup"><span data-stu-id="4ff7c-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="4ff7c-119">Ez a megvalósítás $n-$1 kiegészítő qubits használ.</span><span class="sxs-lookup"><span data-stu-id="4ff7c-119">This implementation uses $n-1$ auxiliary qubits.</span></span>

## <a name="references"></a><span data-ttu-id="4ff7c-120">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="4ff7c-120">References</span></span>

- [<span data-ttu-id="4ff7c-121">*Andrew M. Childs, Dmitrij Maslov, Yunseong Nam, Neil J. Ross, Yuan Su*, arXiv: 1711.10980</span><span class="sxs-lookup"><span data-stu-id="4ff7c-121"> *Andrew M. Childs, Dmitri Maslov, Yunseong Nam, Neil J. Ross, Yuan Su*, arXiv:1711.10980</span></span>](https://arxiv.org/abs/1711.10980)