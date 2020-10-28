---
uid: Microsoft.Quantum.Preparation.PrepareUniformSuperposition
title: PrepareUniformSuperposition művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareUniformSuperposition
qsharp.summary: >-
  Creates a uniform superposition over states that encode 0 through `nIndices - 1`.

  That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$. In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}. \end{align} $$.
ms.openlocfilehash: 8b57a7a02e9f704cf9677574824dfdc93fff25b0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709455"
---
# <a name="prepareuniformsuperposition-operation"></a><span data-ttu-id="5e3ab-102">PrepareUniformSuperposition művelet</span><span class="sxs-lookup"><span data-stu-id="5e3ab-102">PrepareUniformSuperposition operation</span></span>

<span data-ttu-id="5e3ab-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="5e3ab-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="5e3ab-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5e3ab-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5e3ab-105">A 0 és közötti kódolást biztosító állapotok egységes összeosztását hozza létre `nIndices - 1` .</span><span class="sxs-lookup"><span data-stu-id="5e3ab-105">Creates a uniform superposition over states that encode 0 through `nIndices - 1`.</span></span>

<span data-ttu-id="5e3ab-106">Ez azt eredményezi, hogy ez az egységes $U $ a $0 $ és $M-$1 közötti összes számú államban egységes feladatot hoz létre, amely a \ket{0\cdots 0} $ értékű bemeneti állapottal rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="5e3ab-106">That is, this unitary $U$ creates a uniform superposition over all number states $0$ to $M-1$, given an input state $\ket{0\cdots 0}$.</span></span> <span data-ttu-id="5e3ab-107">Más szóval, $ $ \begin{align} U\ket {0} = \frac {1} {\sqrt{m}}\ sum_ {j = 0} ^ {M-1} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="5e3ab-107">In other words, $$ \begin{align} U\ket{0}=\frac{1}{\sqrt{M}}\sum_{j=0}^{M-1}\ket{j}.</span></span>
<span data-ttu-id="5e3ab-108">\end{align} $ $.</span><span class="sxs-lookup"><span data-stu-id="5e3ab-108">\end{align} $$.</span></span>

```qsharp
operation PrepareUniformSuperposition (nIndices : Int, indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a><span data-ttu-id="5e3ab-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5e3ab-109">Input</span></span>

### <a name="nindices--int"></a><span data-ttu-id="5e3ab-110">nIndices: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5e3ab-110">nIndices : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5e3ab-111">Az állapotok kívánt száma $M $ egységben.</span><span class="sxs-lookup"><span data-stu-id="5e3ab-111">The desired number of states $M$ in the uniform superposition.</span></span>


### <a name="indexregister--littleendian"></a><span data-ttu-id="5e3ab-112">indexRegister: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="5e3ab-112">indexRegister : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="5e3ab-113">A qubit-regisztráció, amely a számot tárolja a `LittleEndian` formátumban.</span><span class="sxs-lookup"><span data-stu-id="5e3ab-113">The qubit register that stores the number states in `LittleEndian` format.</span></span>
<span data-ttu-id="5e3ab-114">A regisztrációnak képesnek kell lennie a $M-$1 szám tárolására, és a rendszer azt feltételezi, hogy inicializálva van a $ \ket{0\cdots 0} $ állapotban.</span><span class="sxs-lookup"><span data-stu-id="5e3ab-114">This register must be able to store the number $M-1$, and is assumed to be initialized in the state $\ket{0\cdots 0}$.</span></span>



## <a name="output--unit"></a><span data-ttu-id="5e3ab-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="5e3ab-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="5e3ab-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="5e3ab-116">Remarks</span></span>

<span data-ttu-id="5e3ab-117">A művelet adjointable, de az ilyen esetekben a szükséges, hogy az első esetben egységes feltételt biztosítson `indexRegister` `nIndices` .</span><span class="sxs-lookup"><span data-stu-id="5e3ab-117">The operation is adjointable, but requires that `indexRegister` is in a uniform superposition over the first `nIndices` basis states in that case.</span></span>