---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: ef689c55f966e63a2ab8bcdccf99d9cb5e6d3a4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713725"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="55c3f-102">EstimateTermExpectation művelet</span><span class="sxs-lookup"><span data-stu-id="55c3f-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="55c3f-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="55c3f-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="55c3f-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="55c3f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="55c3f-105">Egy adott Jordan-Wigner Hamilton-kifejezéshez társított energia kiszámítása</span><span class="sxs-lookup"><span data-stu-id="55c3f-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="55c3f-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="55c3f-106">Description</span></span>

<span data-ttu-id="55c3f-107">Ez a művelet becslést készít az egyes mérési operátorokhoz társított elvárások értékéről, és a mintavételezéssel megszorozza azt a megfelelő együtthatóval.</span><span class="sxs-lookup"><span data-stu-id="55c3f-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="55c3f-108">Az eredmények egy olyan változóba vannak összesítve, amely a Jordan-Wigneri időszak energiafogyasztását tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="55c3f-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="55c3f-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="55c3f-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit-adj"></a><span data-ttu-id="55c3f-110">inputStateUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="55c3f-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="55c3f-111">Az állapot előkészítéséhez használt egységes szolgáltatás.</span><span class="sxs-lookup"><span data-stu-id="55c3f-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="55c3f-112">Ops: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="55c3f-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="55c3f-113">A Jordan-Wigner kifejezés mérési operátorai.</span><span class="sxs-lookup"><span data-stu-id="55c3f-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="55c3f-114">coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="55c3f-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="55c3f-115">A Jordan-Wigner kifejezés együtthatói.</span><span class="sxs-lookup"><span data-stu-id="55c3f-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="55c3f-116">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55c3f-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55c3f-117">A molekuláris rendszerek szimulálásához szükséges qubits száma.</span><span class="sxs-lookup"><span data-stu-id="55c3f-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="55c3f-118">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="55c3f-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="55c3f-119">A kifejezés elvárt értékének becsléséhez használandó minták száma.</span><span class="sxs-lookup"><span data-stu-id="55c3f-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="55c3f-120">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="55c3f-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="55c3f-121">Az Jordan-Wigner-kifejezéshez kapcsolódó energia.</span><span class="sxs-lookup"><span data-stu-id="55c3f-121">The energy associated to the Jordan-Wigner term.</span></span>