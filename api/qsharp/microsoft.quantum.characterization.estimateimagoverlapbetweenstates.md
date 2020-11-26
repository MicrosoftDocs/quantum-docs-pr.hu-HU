---
uid: Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates
title: EstimateImagOverlapBetweenStates művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateImagOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.
ms.openlocfilehash: b192abc4ba37d126bf46f94c66cb87fe3bbec4c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216200"
---
# <a name="estimateimagoverlapbetweenstates-operation"></a><span data-ttu-id="410ef-102">EstimateImagOverlapBetweenStates művelet</span><span class="sxs-lookup"><span data-stu-id="410ef-102">EstimateImagOverlapBetweenStates operation</span></span>

<span data-ttu-id="410ef-103">Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="410ef-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="410ef-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="410ef-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="410ef-105">A két művelet, amely az egyes állapotok előkészítését végzi, a megbecsüli az egyes műveletek által előkészített állapotok közötti átfedés képzeletbeli részét.</span><span class="sxs-lookup"><span data-stu-id="410ef-105">Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateImagOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="410ef-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="410ef-106">Input</span></span>

### <a name="commonpreparation--qubit--unit--is-adj"></a><span data-ttu-id="410ef-107">commonPreparation: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="410ef-107">commonPreparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="410ef-108">Egy rögzített bemeneti állapotot előkészítő művelet.</span><span class="sxs-lookup"><span data-stu-id="410ef-108">An operation that prepares a fixed input state.</span></span>


### <a name="preparation1--qubit--unit--is-adj--ctl"></a><span data-ttu-id="410ef-109">preparation1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="410ef-109">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="410ef-110">A két állapot-előkészítési művelet első része, amelyet össze kell hasonlítani.</span><span class="sxs-lookup"><span data-stu-id="410ef-110">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit--is-adj--ctl"></a><span data-ttu-id="410ef-111">preparation2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="410ef-111">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="410ef-112">A két állapot-előkészítési művelet második része, amelyet össze kell hasonlítani.</span><span class="sxs-lookup"><span data-stu-id="410ef-112">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="410ef-113">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="410ef-113">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="410ef-114">Azon qubits száma, amelyeken a, és az összes tevékenység szerepel `commonPreparation` `preparation1` `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="410ef-114">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="410ef-115">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="410ef-115">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="410ef-116">Az átfedések becsléséhez használni kívánt mérések száma.</span><span class="sxs-lookup"><span data-stu-id="410ef-116">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="410ef-117">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="410ef-117">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="410ef-118">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="410ef-118">Remarks</span></span>

<span data-ttu-id="410ef-119">Ez a művelet a Hadamard teszttel keresi a $ $ \begin{align} \braket{\psi-beli képzeletbeli részét. V ^ {\dagger} U | \psi} \end{align} $ $, ahol a $ \ket{\psi} $ a által előkészített állapot `commonPreparation` , $U $ a művelet egységes ábrázolása `preparation1` , és a $V $ értéknek megfelelő `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="410ef-119">This operation uses the Hadamard test to find the imaginary part of $$ \begin{align} \braket{\psi | V^{\dagger} U | \psi} \end{align} $$ where $\ket{\psi}$ is the state prepared by `commonPreparation`, $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="references"></a><span data-ttu-id="410ef-120">Hivatkozások</span><span class="sxs-lookup"><span data-stu-id="410ef-120">References</span></span>

- <span data-ttu-id="410ef-121">Aharonov *et al.* [Quant – pH/0511096](https://arxiv.org/abs/quant-ph/0511096).</span><span class="sxs-lookup"><span data-stu-id="410ef-121">Aharonov *et al.* [quant-ph/0511096](https://arxiv.org/abs/quant-ph/0511096).</span></span>

## <a name="see-also"></a><span data-ttu-id="410ef-122">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="410ef-122">See Also</span></span>

- [<span data-ttu-id="410ef-123">Microsoft. Quantum. jellemzés. EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="410ef-123">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="410ef-124">Microsoft. Quantum. jellemzés. EstimateOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="410ef-124">Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)