---
uid: Microsoft.Quantum.Canon.TrotterArbitraryImplCA
title: TrotterArbitraryImplCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterArbitraryImplCA
qsharp.summary: Recursive implementation of even-order Trotter–Suzuki integrator.
ms.openlocfilehash: 2abfbb9d51a98d8ede1b0835875a3771ffda0691
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204725"
---
# <a name="trotterarbitraryimplca-operation"></a><span data-ttu-id="b716e-102">TrotterArbitraryImplCA művelet</span><span class="sxs-lookup"><span data-stu-id="b716e-102">TrotterArbitraryImplCA operation</span></span>

<span data-ttu-id="b716e-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b716e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b716e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b716e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b716e-105">A páros-Order Trotter – Suzuki integrátor rekurzív megvalósítása.</span><span class="sxs-lookup"><span data-stu-id="b716e-105">Recursive implementation of even-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation TrotterArbitraryImplCA<'T> (order : Int, (nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="b716e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b716e-106">Input</span></span>

### <a name="order--int"></a><span data-ttu-id="b716e-107">megrendelés: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b716e-107">order : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b716e-108">Trotter-Suzuki integrátor sorrendje.</span><span class="sxs-lookup"><span data-stu-id="b716e-108">Order of Trotter-Suzuki integrator.</span></span>


### <a name="nsteps--int"></a><span data-ttu-id="b716e-109">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b716e-109">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b716e-110">A felbontani kívánt műveletek száma az idő lépésekben.</span><span class="sxs-lookup"><span data-stu-id="b716e-110">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="b716e-111">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="b716e-111">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="b716e-112">Egy művelet, amely elfogad egy index bemenetet (típus `Int` ) és egy időbemenetet (típus) `Double` és egy kvantum-regisztrációt (típus `'T` ) a dekompozícióhoz.</span><span class="sxs-lookup"><span data-stu-id="b716e-112">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="b716e-113">stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b716e-113">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b716e-114">Szorzó a szimuláció egyes lépéseinek méretéhez.</span><span class="sxs-lookup"><span data-stu-id="b716e-114">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="b716e-115">cél: nem</span><span class="sxs-lookup"><span data-stu-id="b716e-115">target : 'T</span></span>

<span data-ttu-id="b716e-116">Az Operations műveletet elvégező kvantum-regisztráció.</span><span class="sxs-lookup"><span data-stu-id="b716e-116">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b716e-117">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b716e-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b716e-118">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="b716e-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b716e-119">Nem</span><span class="sxs-lookup"><span data-stu-id="b716e-119">'T</span></span>

<span data-ttu-id="b716e-120">Az a típus, amely az egyes időpontokban cselekszik; általában a `Qubit[]` vagy a `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="b716e-120">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>