---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 3f0ff5037b1424abb6fb318bd49ffd89f545822d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224649"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="f578d-102">EstimateTermExpectation művelet</span><span class="sxs-lookup"><span data-stu-id="f578d-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="f578d-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="f578d-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="f578d-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f578d-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="f578d-105">Egy adott Jordan-Wigner Hamilton-kifejezéshez társított energia kiszámítása</span><span class="sxs-lookup"><span data-stu-id="f578d-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="f578d-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="f578d-106">Description</span></span>

<span data-ttu-id="f578d-107">Ez a művelet becslést készít az egyes mérési operátorokhoz társított elvárások értékéről, és a mintavételezéssel megszorozza azt a megfelelő együtthatóval.</span><span class="sxs-lookup"><span data-stu-id="f578d-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="f578d-108">Az eredmények egy olyan változóba vannak összesítve, amely a Jordan-Wigneri időszak energiafogyasztását tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="f578d-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="f578d-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f578d-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit--is-adj"></a><span data-ttu-id="f578d-110">inputStateUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f578d-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="f578d-111">Az állapot előkészítéséhez használt egységes szolgáltatás.</span><span class="sxs-lookup"><span data-stu-id="f578d-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="f578d-112">Ops: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="f578d-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="f578d-113">A Jordan-Wigner kifejezés mérési operátorai.</span><span class="sxs-lookup"><span data-stu-id="f578d-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="f578d-114">coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="f578d-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="f578d-115">A Jordan-Wigner kifejezés együtthatói.</span><span class="sxs-lookup"><span data-stu-id="f578d-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="f578d-116">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f578d-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f578d-117">A molekuláris rendszerek szimulálásához szükséges qubits száma.</span><span class="sxs-lookup"><span data-stu-id="f578d-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="f578d-118">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f578d-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f578d-119">A kifejezés elvárt értékének becsléséhez használandó minták száma.</span><span class="sxs-lookup"><span data-stu-id="f578d-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="f578d-120">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f578d-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f578d-121">Az Jordan-Wigner-kifejezéshez kapcsolódó energia.</span><span class="sxs-lookup"><span data-stu-id="f578d-121">The energy associated to the Jordan-Wigner term.</span></span>