---
uid: Microsoft.Quantum.Canon.DecomposedIntoTimeStepsCA
title: DecomposedIntoTimeStepsCA függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DecomposedIntoTimeStepsCA
qsharp.summary: Returns an operation implementing the Trotter–Suzuki integrator for a given operation.
ms.openlocfilehash: cfd563c1c6350255364de1e227442624acc98c22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716342"
---
# <a name="decomposedintotimestepsca-function"></a><span data-ttu-id="77106-102">DecomposedIntoTimeStepsCA függvény</span><span class="sxs-lookup"><span data-stu-id="77106-102">DecomposedIntoTimeStepsCA function</span></span>

<span data-ttu-id="77106-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="77106-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="77106-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="77106-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="77106-105">Egy adott művelethez tartozó Trotter – Suzuki integrátort megvalósító műveletet ad vissza.</span><span class="sxs-lookup"><span data-stu-id="77106-105">Returns an operation implementing the Trotter–Suzuki integrator for a given operation.</span></span>

```qsharp
function DecomposedIntoTimeStepsCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), trotterOrder : Int) : ((Double, 'T) => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="77106-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="77106-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="77106-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="77106-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="77106-108">A felbontani kívánt műveletek száma az idő lépésekben.</span><span class="sxs-lookup"><span data-stu-id="77106-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit-adj--ctl"></a><span data-ttu-id="77106-109">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="77106-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="77106-110">Egy művelet, amely elfogad egy index bemenetet (típus `Int` ) és egy időbemenetet (típus `Double` ) a dekompozícióhoz.</span><span class="sxs-lookup"><span data-stu-id="77106-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) for decomposition.</span></span>


### <a name="trotterorder--int"></a><span data-ttu-id="77106-111">trotterOrder: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="77106-111">trotterOrder : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="77106-112">Kiválasztja a használni kívánt Trotter-Suzuki-integrátor sorrendjét.</span><span class="sxs-lookup"><span data-stu-id="77106-112">Selects the order of the Trotter–Suzuki integrator to be used.</span></span>
<span data-ttu-id="77106-113">1. megrendelés és a 2., 4., 6. rendelés,... jelenleg támogatottak.</span><span class="sxs-lookup"><span data-stu-id="77106-113">Order 1 and even orders 2, 4, 6,... are currently supported.</span></span>



## <a name="output--doublet--unit-adj--ctl"></a><span data-ttu-id="77106-114">Kimenet: ([Double](xref:microsoft.quantum.lang-ref.double), 't) => [egység](xref:microsoft.quantum.lang-ref.unit) : Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="77106-114">Output : ([Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="77106-115">A Trotter – Suzuki integrátor egységes megvalósítását adja vissza, ahol az első paraméter az `Double` integrációs lépés mérete, a második paraméter pedig a cél.</span><span class="sxs-lookup"><span data-stu-id="77106-115">Returns a unitary implementing the Trotter–Suzuki integrator, where the first parameter `Double` is the integration step size, and the second parameter is the target acted upon.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="77106-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="77106-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="77106-117">Nem</span><span class="sxs-lookup"><span data-stu-id="77106-117">'T</span></span>

<span data-ttu-id="77106-118">Az a típus, amely az egyes időpontokban cselekszik; általában a `Qubit[]` vagy a `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="77106-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>

## <a name="remarks"></a><span data-ttu-id="77106-119">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="77106-119">Remarks</span></span>

<span data-ttu-id="77106-120">Ha `order` egyenlő értékűre van meghívva `1` , ez a függvény egy olyan műveletet ad vissza, amelyet a legalacsonyabb rendű Trotter – Suzuki integrátor $ $ \begin{align} S_1 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_j \lambda}, \end{align} $ $, ahol követte a [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139) jelölését, és hagyja, hogy a $ \lambda $ legyen az evolúciós idő (amelyet a visszaadott művelet első bemenete képvisel), és engedje, hogy \{ a $ H_j \} _ {j = 1} ^ {m} $ legyen a (ferde Hermitian) dinamikus generátorok olyan készlete, amely integrálva van, így `op(j, lambda, _)` az egységes operátor szimulálja $e ^ {H_j \lambda} $.</span><span class="sxs-lookup"><span data-stu-id="77106-120">When called with `order` equal to `1`, this function returns an operation that can be simulated by the lowest-order Trotter–Suzuki integrator $$ \begin{align} S_1(\lambda) = \prod_{j = 1}^{m} e^{H_j \lambda}, \end{align} $$ where we have followed the notation of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139) and let $\lambda$ be the evolution time (represented by the first input of the returned operation), and have let $\{H_j\}_{j = 1}^{m}$ be the set of (skew-Hermitian) dynamical generators being integrated such that `op(j, lambda, _)` is simulated by the unitary operator $e^{H_j \lambda}$.</span></span>

<span data-ttu-id="77106-121">Hasonlóképpen, a `order` `2` -ból a második sorrend szimmetrikus Trotter – Suzuki integrátor $ $ \begin{align} S_2 (\lambda) = \ prod_ {j = 1} ^ {m} e ^ {H_k \lambda/2} \ prod_ {j ' = m} ^ {1} e ^ {H_ {j '} \lambda/2}.</span><span class="sxs-lookup"><span data-stu-id="77106-121">Similarly, an `order` of `2` returns the second-order symmetric Trotter–Suzuki integrator $$ \begin{align} S_2(\lambda) = \prod_{j = 1}^{m} e^{H_k \lambda / 2} \prod_{j' = m}^{1} e^{H_{j'} \lambda / 2}.</span></span>
<span data-ttu-id="77106-122">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="77106-122">\end{align} $$</span></span>

<span data-ttu-id="77106-123">A `order` [Quant-pH/0508139](https://arxiv.org/abs/quant-ph/0508139)rekurzív felépítése révén a rendszer még nagyobb értékeket is megvalósít.</span><span class="sxs-lookup"><span data-stu-id="77106-123">Higher even values of `order` are implemented using the recursive construction of [quant-ph/0508139](https://arxiv.org/abs/quant-ph/0508139).</span></span>

## <a name="references"></a><span data-ttu-id="77106-124">Referencia</span><span class="sxs-lookup"><span data-stu-id="77106-124">References</span></span>

- [<span data-ttu-id="77106-125">*D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders*</span><span class="sxs-lookup"><span data-stu-id="77106-125"> *D. W. Berry, G. Ahokas, R. Cleve, B. C. Sanders* </span></span>](https://arxiv.org/abs/quant-ph/0508139)