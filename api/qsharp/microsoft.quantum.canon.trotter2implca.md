---
uid: Microsoft.Quantum.Canon.Trotter2ImplCA
title: Trotter2ImplCA művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Trotter2ImplCA
qsharp.summary: Implementation of the second-order Trotter–Suzuki integrator.
ms.openlocfilehash: 0e3a7e53a4d415e6b5af81d9bb3f52cddf36c4b3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204742"
---
# <a name="trotter2implca-operation"></a><span data-ttu-id="8f14a-102">Trotter2ImplCA művelet</span><span class="sxs-lookup"><span data-stu-id="8f14a-102">Trotter2ImplCA operation</span></span>

<span data-ttu-id="8f14a-103">Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="8f14a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="8f14a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="8f14a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="8f14a-105">A második rendű Trotter – Suzuki integrátor implementálása.</span><span class="sxs-lookup"><span data-stu-id="8f14a-105">Implementation of the second-order Trotter–Suzuki integrator.</span></span>

```qsharp
operation Trotter2ImplCA<'T> ((nSteps : Int, op : ((Int, Double, 'T) => Unit is Adj + Ctl)), stepSize : Double, target : 'T) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="8f14a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8f14a-106">Input</span></span>

### <a name="nsteps--int"></a><span data-ttu-id="8f14a-107">nSteps: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8f14a-107">nSteps : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8f14a-108">A felbontani kívánt műveletek száma az idő lépésekben.</span><span class="sxs-lookup"><span data-stu-id="8f14a-108">The number of operations to be decomposed into time steps.</span></span>


### <a name="op--intdoublet--unit--is-adj--ctl"></a><span data-ttu-id="8f14a-109">op: ([int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double), 't) => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="8f14a-109">op : ([Int](xref:microsoft.quantum.lang-ref.int),[Double](xref:microsoft.quantum.lang-ref.double),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="8f14a-110">Egy művelet, amely elfogad egy index bemenetet (típus `Int` ) és egy időbemenetet (típus) `Double` és egy kvantum-regisztrációt (típus `'T` ) a dekompozícióhoz.</span><span class="sxs-lookup"><span data-stu-id="8f14a-110">An operation which accepts an index input (type `Int`) and a time input (type `Double`) and a quantum register (type `'T`) for decomposition.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="8f14a-111">stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8f14a-111">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8f14a-112">Szorzó a szimuláció egyes lépéseinek méretéhez.</span><span class="sxs-lookup"><span data-stu-id="8f14a-112">Multiplier on size of each step of the simulation.</span></span>


### <a name="target--t"></a><span data-ttu-id="8f14a-113">cél: nem</span><span class="sxs-lookup"><span data-stu-id="8f14a-113">target : 'T</span></span>

<span data-ttu-id="8f14a-114">Az Operations műveletet elvégező kvantum-regisztráció.</span><span class="sxs-lookup"><span data-stu-id="8f14a-114">A quantum register on which the operations act.</span></span>



## <a name="output--unit"></a><span data-ttu-id="8f14a-115">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="8f14a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="8f14a-116">Típusparaméterek</span><span class="sxs-lookup"><span data-stu-id="8f14a-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8f14a-117">Nem</span><span class="sxs-lookup"><span data-stu-id="8f14a-117">'T</span></span>

<span data-ttu-id="8f14a-118">Az a típus, amely az egyes időpontokban cselekszik; általában a `Qubit[]` vagy a `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="8f14a-118">The type which each time step should act upon; typically, either `Qubit[]` or `Qubit`.</span></span>