---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 7df4c1ea859140a669698434c6f8a786ea3bc2ea
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835673"
---
# <a name="estimatetermexpectation-operation"></a><span data-ttu-id="6f1d1-102">EstimateTermExpectation művelet</span><span class="sxs-lookup"><span data-stu-id="6f1d1-102">EstimateTermExpectation operation</span></span>

<span data-ttu-id="6f1d1-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="6f1d1-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="6f1d1-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6f1d1-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="6f1d1-105">Egy adott Jordan-Wigner Hamilton-kifejezéshez társított energia kiszámítása</span><span class="sxs-lookup"><span data-stu-id="6f1d1-105">Computes the energy associated to a given Jordan-Wigner Hamiltonian term</span></span>

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="6f1d1-106">Leírás</span><span class="sxs-lookup"><span data-stu-id="6f1d1-106">Description</span></span>

<span data-ttu-id="6f1d1-107">Ez a művelet becslést készít az egyes mérési operátorokhoz társított elvárások értékéről, és a mintavételezéssel megszorozza azt a megfelelő együtthatóval.</span><span class="sxs-lookup"><span data-stu-id="6f1d1-107">This operation estimates the expectation value associated to each measurement operator and multiplies it by the corresponding coefficient, using sampling.</span></span>
<span data-ttu-id="6f1d1-108">Az eredmények egy olyan változóba vannak összesítve, amely a Jordan-Wigneri időszak energiafogyasztását tartalmazza.</span><span class="sxs-lookup"><span data-stu-id="6f1d1-108">The results are aggregated into a variable containing the energy of the Jordan-Wigner term.</span></span>

## <a name="input"></a><span data-ttu-id="6f1d1-109">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6f1d1-109">Input</span></span>

### <a name="inputstateunitary--qubit--unit--is-adj"></a><span data-ttu-id="6f1d1-110">inputStateUnitary: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6f1d1-110">inputStateUnitary : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="6f1d1-111">Az állapot előkészítéséhez használt egységes szolgáltatás.</span><span class="sxs-lookup"><span data-stu-id="6f1d1-111">The unitary used for state preparation.</span></span>


### <a name="ops--pauli"></a><span data-ttu-id="6f1d1-112">Ops: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []</span><span class="sxs-lookup"><span data-stu-id="6f1d1-112">ops : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[][]</span></span>

<span data-ttu-id="6f1d1-113">A Jordan-Wigner kifejezés mérési operátorai.</span><span class="sxs-lookup"><span data-stu-id="6f1d1-113">The measurement operators of the Jordan-Wigner term.</span></span>


### <a name="coeffs--double"></a><span data-ttu-id="6f1d1-114">coeffs: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="6f1d1-114">coeffs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="6f1d1-115">A Jordan-Wigner kifejezés együtthatói.</span><span class="sxs-lookup"><span data-stu-id="6f1d1-115">The coefficients of the Jordan-Wigner term.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="6f1d1-116">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6f1d1-116">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6f1d1-117">A molekuláris rendszerek szimulálásához szükséges qubits száma.</span><span class="sxs-lookup"><span data-stu-id="6f1d1-117">The number of qubits required to simulate the molecular system.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="6f1d1-118">nSamples: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6f1d1-118">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6f1d1-119">A kifejezés elvárt értékének becsléséhez használandó minták száma.</span><span class="sxs-lookup"><span data-stu-id="6f1d1-119">The number of samples to use for the estimation of the term expectation.</span></span>



## <a name="output--double"></a><span data-ttu-id="6f1d1-120">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6f1d1-120">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6f1d1-121">Az Jordan-Wigner-kifejezéshez kapcsolódó energia.</span><span class="sxs-lookup"><span data-stu-id="6f1d1-121">The energy associated to the Jordan-Wigner term.</span></span>