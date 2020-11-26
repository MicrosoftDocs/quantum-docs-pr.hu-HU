---
uid: Microsoft.Quantum.Canon.MultiplexOperationsBruteForceFromGenerator
title: MultiplexOperationsBruteForceFromGenerator művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: MultiplexOperationsBruteForceFromGenerator
qsharp.summary: >-
  Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.

  $U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.
ms.openlocfilehash: a700cffbd8fe8be01fdb7344cc9d4b02a4900174
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206000"
---
# <a name="multiplexoperationsbruteforcefromgenerator-operation"></a><span data-ttu-id="dc5be-102">MultiplexOperationsBruteForceFromGenerator művelet</span><span class="sxs-lookup"><span data-stu-id="dc5be-102">MultiplexOperationsBruteForceFromGenerator operation</span></span>

<span data-ttu-id="dc5be-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="dc5be-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="dc5be-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="dc5be-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="dc5be-105">A szorzásra vezérelt, egységes művelet $U $ értéket alkalmazza, amely egy egységes $V-_j $-t alkalmaz, ha n-qubit számú állapotot ($ \ket{j} $) vezérel.</span><span class="sxs-lookup"><span data-stu-id="dc5be-105">Applies multiply-controlled unitary operation $U$ that applies a unitary $V_j$ when controlled by n-qubit number state $\ket{j}$.</span></span>

<span data-ttu-id="dc5be-106">$U = \sum ^ {N-1} _ {j = 0} \ket{j}\bra{j}\otimes V_j $.</span><span class="sxs-lookup"><span data-stu-id="dc5be-106">$U = \sum^{N-1}_{j=0}\ket{j}\bra{j}\otimes V_j$.</span></span>

```qsharp
operation MultiplexOperationsBruteForceFromGenerator<'T> (unitaryGenerator : (Int, (Int -> ('T => Unit is Adj + Ctl))), index : Microsoft.Quantum.Arithmetic.LittleEndian, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="dc5be-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="dc5be-107">Input</span></span>

### <a name="unitarygenerator--intint---t--unit--is-adj--ctl"></a><span data-ttu-id="dc5be-108">unitaryGenerator: ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int) -> 't => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL)</span><span class="sxs-lookup"><span data-stu-id="dc5be-108">unitaryGenerator : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int) -> 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

<span data-ttu-id="dc5be-109">Egy rekord, amelyben az első elem `Int` a unitaries $N $, a második elem `(Int -> ('T => () is Adj + Ctl))` pedig egy függvény, amely egy egész $j $ értéket vesz igénybe $ [0, N-1] $ értékben, és az egységes művelet $V _j $ értéket adja eredményül.</span><span class="sxs-lookup"><span data-stu-id="dc5be-109">A tuple where the first element `Int` is the number of unitaries $N$, and the second element `(Int -> ('T => () is Adj + Ctl))` is a function that takes an integer $j$ in $[0,N-1]$ and outputs the unitary operation $V_j$.</span></span>


### <a name="index--littleendian"></a><span data-ttu-id="dc5be-110">index: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="dc5be-110">index : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="dc5be-111">$n $-qubit-vezérlő regisztrálása, amely kis endian formátumban kódolja a szám állapotot $ \ket{j} $ értékre.</span><span class="sxs-lookup"><span data-stu-id="dc5be-111">$n$-qubit control register that encodes number states $\ket{j}$ in little-endian format.</span></span>


### <a name="target--t"></a><span data-ttu-id="dc5be-112">cél: nem</span><span class="sxs-lookup"><span data-stu-id="dc5be-112">target : 'T</span></span>

<span data-ttu-id="dc5be-113">Az általános qubit regisztrálja, hogy $V _j $ működik.</span><span class="sxs-lookup"><span data-stu-id="dc5be-113">Generic qubit register that $V_j$ acts on.</span></span>



## <a name="output--unit"></a><span data-ttu-id="dc5be-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="dc5be-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="dc5be-115">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="dc5be-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="dc5be-116">Nem</span><span class="sxs-lookup"><span data-stu-id="dc5be-116">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="dc5be-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="dc5be-117">Remarks</span></span>

<span data-ttu-id="dc5be-118">`coefficients` Ha kevesebb, mint $2 ^ n $ érték van megadva, akkor az azonosító elemek kitöltése megtörténik.</span><span class="sxs-lookup"><span data-stu-id="dc5be-118">`coefficients` will be padded with identity elements if fewer than $2^n$ are specified.</span></span> <span data-ttu-id="dc5be-119">Ez a verzió közvetlenül az n vezérelt, egységes operátorok használatával valósítható meg.</span><span class="sxs-lookup"><span data-stu-id="dc5be-119">This version is implemented directly by looping through n-controlled unitary operators.</span></span>