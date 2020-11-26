---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: EstimateOverlapBetweenStates művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: 07693ccf4b8e7bbde189674d9e6b2bf7f92222f6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204300"
---
# <a name="estimateoverlapbetweenstates-operation"></a><span data-ttu-id="61b50-102">EstimateOverlapBetweenStates művelet</span><span class="sxs-lookup"><span data-stu-id="61b50-102">EstimateOverlapBetweenStates operation</span></span>

<span data-ttu-id="61b50-103">Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="61b50-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="61b50-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="61b50-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="61b50-105">A két művelet, amely az egyes példányok előkészítését végzi, az egyes műveletek által előkészített állapotok közötti négyzetes átfedést becsüli.</span><span class="sxs-lookup"><span data-stu-id="61b50-105">Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.</span></span>

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="61b50-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="61b50-106">Input</span></span>

### <a name="preparation1--qubit--unit--is-adj"></a><span data-ttu-id="61b50-107">preparation1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61b50-107">preparation1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="61b50-108">A két állapot-előkészítési művelet első része, amelyet össze kell hasonlítani.</span><span class="sxs-lookup"><span data-stu-id="61b50-108">The first of the two state preparation operations to be compared.</span></span>


### <a name="preparation2--qubit--unit--is-adj"></a><span data-ttu-id="61b50-109">preparation2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61b50-109">preparation2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="61b50-110">A két állapot-előkészítési művelet második része, amelyet össze kell hasonlítani.</span><span class="sxs-lookup"><span data-stu-id="61b50-110">The second of the two state preparation operations to be compared.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="61b50-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="61b50-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="61b50-112">Azon qubits száma, amelyeken a, és az összes tevékenység szerepel `commonPreparation` `preparation1` `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="61b50-112">The number of qubits on which `commonPreparation`, `preparation1`, and `preparation2` all act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="61b50-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="61b50-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="61b50-114">Az átfedések becsléséhez használni kívánt mérések száma.</span><span class="sxs-lookup"><span data-stu-id="61b50-114">The number of measurements to use in estimating the overlap.</span></span>



## <a name="output--double"></a><span data-ttu-id="61b50-115">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="61b50-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>



## <a name="remarks"></a><span data-ttu-id="61b50-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="61b50-116">Remarks</span></span>

<span data-ttu-id="61b50-117">A művelet a SWAP teszt használatával keresi a $ $ \begin{align} \left | \braket{00\cdots 0 | V ^ {\dagger} U | 00 \ cdots 0} \right | ^ 2 \end{align} $ $, ahol a $U $ a művelet egységes ábrázolása `preparation1` , és a $V $ értéknek felel meg `preparation2` .</span><span class="sxs-lookup"><span data-stu-id="61b50-117">This operation uses the SWAP test to find $$ \begin{align} \left| \braket{00\cdots 0 | V^{\dagger} U | 00\cdots 0} \right|^2 \end{align} $$ where $U$ is the unitary representation of the action of `preparation1`, and where $V$ corresponds to `preparation2`.</span></span>

## <a name="see-also"></a><span data-ttu-id="61b50-118">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="61b50-118">See Also</span></span>

- [<span data-ttu-id="61b50-119">Microsoft. Quantum. jellemzés. EstimateRealOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="61b50-119">Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [<span data-ttu-id="61b50-120">Microsoft. Quantum. jellemzés. EstimateImagOverlapBetweenStates</span><span class="sxs-lookup"><span data-stu-id="61b50-120">Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates</span></span>](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)