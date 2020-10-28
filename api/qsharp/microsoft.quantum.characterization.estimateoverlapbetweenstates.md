---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: EstimateOverlapBetweenStates művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: 58a367c7ff7d13ac5c1eb1588fb8dac66414776c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714998"
---
# <a name="estimateoverlapbetweenstates-operation"></a><span data-ttu-id="83766-102">EstimateOverlapBetweenStates művelet</span><span class="sxs-lookup"><span data-stu-id="83766-102">EstimateOverlapBetweenStates operation</span></span>

<span data-ttu-id="83766-103">Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="83766-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="83766-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="83766-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="83766-105">A két művelet, amely az egyes példányok előkészítését végzi, az egyes műveletek által előkészített állapotok közötti négyzetes átfedést becsüli.</span><span class="sxs-lookup"><span data-stu-id="83766-105">Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="83766-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="83766-106">Input</span></span>

### <a name="preparation1--qubit--unit-adj"></a><span data-ttu-id="83766-107">preparation1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="83766-107">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="83766-108">A két állapot-előkészítési művelet első része, amelyet össze kell hasonlítani.</span><span class="sxs-lookup"><span data-stu-id="83766-108">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit-adj"></a><span data-ttu-id="83766-109">preparation2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="83766-109">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="83766-110">A két állapot-előkészítési művelet második része, amelyet össze kell hasonlítani.</span><span class="sxs-lookup"><span data-stu-id="83766-110">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="83766-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="83766-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="83766-112">Azon qubits száma, amelyeken a, és az összes tevékenység szerepel `commonPreparation` `preparation1` `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="83766-112">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="83766-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="83766-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="83766-114">Az átfedések becsléséhez használni kívánt mérések száma.</span><span class="sxs-lookup"><span data-stu-id="83766-114">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="83766-115">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="83766-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="83766-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="83766-116">Remarks</span></span>

<span data-ttu-id="83766-117">A művelet a SWAP teszt használatával keresi a $ $ \begin{align} \left | \braket{00\cdots 0 | V ^ {\dagger} U | 00 \ cdots 0} \right | ^ 2 \end{align} $ $, ahol a $U $ a művelet egységes ábrázolása `preparation1` , és a $V $ értéknek felel meg `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="83766-117">This operation uses the SWAP test to find $$ \begin{align} \left| \braket{00\cdots 0 | V^{\dagger} U | 00\cdots 0} \right|^2 \end{align} $$ where $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="see-also"></a><span data-ttu-id="83766-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="83766-118">See Also</span></span>

- [<span data-ttu-id="83766-119">Microsoft. Quantum. jellemzés. EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="83766-119">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="83766-120">Microsoft. Quantum. jellemzés. EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="83766-120">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)