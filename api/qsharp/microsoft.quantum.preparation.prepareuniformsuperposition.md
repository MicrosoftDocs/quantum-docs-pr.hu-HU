---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: dc9d4ce1638b397748cafaa757241ce78633c67c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854319"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="d3a10-102">PrepareUniformSuperposition művelet</span><span class="sxs-lookup"><span data-stu-id="d3a10-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="d3a10-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="d3a10-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="d3a10-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d3a10-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d3a10-105">A 0 és közötti kódolást biztosító állapotok egységes összeosztását hozza létre `nIndices - 1` .</span><span class="sxs-lookup"><span data-stu-id="d3a10-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="d3a10-106">Ez azt eredményezi, hogy ez az egységes $U $ a $0 $ és $M-$1 közötti összes számú államban egységes feladatot hoz létre, amely a \ket{0\cdots 0} $ értékű bemeneti állapottal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="d3a10-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="d3a10-107">Más szóval, $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="d3a10-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="d3a10-108">\end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="d3a10-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="d3a10-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d3a10-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="d3a10-110">nIndices: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d3a10-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d3a10-111">Az állapotok kívánt száma $M $ egységben.</span><span class="sxs-lookup"><span data-stu-id="d3a10-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="d3a10-112">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="d3a10-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="d3a10-113">A qubit-regisztráció, amely a számot tárolja a `LittleEndian` formátumban.</span><span class="sxs-lookup"><span data-stu-id="d3a10-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="d3a10-114">A regisztrációnak képesnek kell lennie a $M-$1 szám tárolására, és a rendszer azt feltételezi, hogy inicializálva van a $ \ket{0\cdots 0} $ állapotban.</span><span class="sxs-lookup"><span data-stu-id="d3a10-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d3a10-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d3a10-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="d3a10-116">Példa</span><span class="sxs-lookup"><span data-stu-id="d3a10-116">Example</span></span>

<span data-ttu-id="d3a10-117">Az alábbi példa a $ \frac {1} {\sqrt {6} } \ sum_ {j = 0} ^ \ket{j} $ értéket állítja elő {5} $3 $ qubits.</span><span class="sxs-lookup"><span data-stu-id="d3a10-117">The following example prepares the state $\frac{1}{\sqrt{6}}\sum_{j=0}^{5}\ket{j}$ on $3$ qubits.</span></span>

```qsharp
let nIndices = 6;
using(indexRegister = Qubit[3]) {
    PrepareUniformSuperposition(nIndices, LittleEndian(indexRegister));
    // ...
}
```

## <a name="remarks"></a><span data-ttu-id="d3a10-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d3a10-118">Remarks</span></span>

<span data-ttu-id="d3a10-119">A művelet adjointable, de az ilyen esetekben a szükséges, hogy az első esetben egységes feltételt biztosítson `indexRegister` `nIndices` .</span><span class="sxs-lookup"><span data-stu-id="d3a10-119">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>