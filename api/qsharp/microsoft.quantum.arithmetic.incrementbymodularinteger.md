---
uid: Microsoft.Quantum.Arithmetic.IncrementByModularInteger
title: IncrementByModularInteger művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: IncrementByModularInteger
qsharp.summary: Performs a modular increment of a qubit register by an integer constant.
ms.openlocfilehash: f5bacef299ab0b3627e757abdcaa798cf9b2e7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846602"
---
# <a name="incrementbymodularinteger-operation"></a><span data-ttu-id="d4167-102">IncrementByModularInteger művelet</span><span class="sxs-lookup"><span data-stu-id="d4167-102">IncrementByModularInteger operation</span></span>

<span data-ttu-id="d4167-103">Névtér: [Microsoft. Quantum. aritmetika](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="d4167-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="d4167-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d4167-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d4167-105">Egy qubit-regiszter moduláris növekményét hajtja végre egy egész állandó értékkel.</span><span class="sxs-lookup"><span data-stu-id="d4167-105">Performs a modular increment of a qubit register by an integer constant.</span></span>

```qsharp
operation IncrementByModularInteger (increment : Int, modulus : Int, target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d4167-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="d4167-106">Description</span></span>

<span data-ttu-id="d4167-107">`increment`$A $, `modulus` $N $ és Integer szerint, $y $ kódolással jelezze nekünk `target` .</span><span class="sxs-lookup"><span data-stu-id="d4167-107">Let us denote `increment` by $a$, `modulus` by $N$ and integer encoded in `target` by $y$.</span></span>
<span data-ttu-id="d4167-108">Ezután a művelet a következő átalakítást hajtja végre: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} egész számok kódolása kis endian formátumban történik.</span><span class="sxs-lookup"><span data-stu-id="d4167-108">Then the operation performs the following transformation: \begin{align} \ket{y} \mapsto \ket{(y + a) \operatorname{mod} N} \end{align} Integers are encoded in little-endian format.</span></span>

## <a name="input"></a><span data-ttu-id="d4167-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d4167-109">Input</span></span>

### <a name="increment--int"></a><span data-ttu-id="d4167-110">növekmény: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d4167-110">increment : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d4167-111">$A $ számú növekményt $y $ értékre kell felvenni.</span><span class="sxs-lookup"><span data-stu-id="d4167-111">Integer increment $a$ to be added to $y$.</span></span>


### <a name="modulus--int"></a><span data-ttu-id="d4167-112">modulus: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d4167-112">modulus : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d4167-113">Egész $N $, hogy a mods $y + a $.</span><span class="sxs-lookup"><span data-stu-id="d4167-113">Integer $N$ that mods $y + a$.</span></span>


### <a name="target--littleendian"></a><span data-ttu-id="d4167-114">cél: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d4167-114">target : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d4167-115">Egész szám $y $ `LittleEndian` formátumban, amelyet `increment` $a $ hozzáad a következőhöz:.</span><span class="sxs-lookup"><span data-stu-id="d4167-115">Integer $y$ in `LittleEndian` format that `increment` $a$ is added to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d4167-116">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d4167-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="d4167-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d4167-117">Remarks</span></span>

<span data-ttu-id="d4167-118">Feltételezi, hogy a célként megadott kezdeti érték kisebb, mint $N $, és hogy a növekmény $a $ értéke kisebb, mint $N $.</span><span class="sxs-lookup"><span data-stu-id="d4167-118">Assumes that the initial value of target is less than $N$ and that the increment $a$ is less than $N$.</span></span>
<span data-ttu-id="d4167-119">Figyelje meg, hogy <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> ugyanazokat a műveleteket hajtja végre `PhaseLittleEndian` .</span><span class="sxs-lookup"><span data-stu-id="d4167-119">Note that <xref:microsoft.quantum.arithmetic.incrementphasebymodularinteger> implements the same operation in the `PhaseLittleEndian` basis.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4167-120">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="d4167-120">See Also</span></span>

- [<span data-ttu-id="d4167-121">Microsoft. Quantum. aritmetika. IncrementPhaseByModularInteger</span><span class="sxs-lookup"><span data-stu-id="d4167-121">Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger</span></span>](xref:Microsoft.Quantum.Arithmetic.IncrementPhaseByModularInteger)