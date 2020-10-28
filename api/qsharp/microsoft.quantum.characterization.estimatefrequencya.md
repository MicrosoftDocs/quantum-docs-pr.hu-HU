---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: EstimateFrequencyA művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 88f0a237975c158bffcc015f79d2134b210ce83b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92715068"
---
# <a name="estimatefrequencya-operation"></a><span data-ttu-id="edb4c-102">EstimateFrequencyA művelet</span><span class="sxs-lookup"><span data-stu-id="edb4c-102">EstimateFrequencyA operation</span></span>

<span data-ttu-id="edb4c-103">Névtér: [Microsoft. Quantum. jellemzés](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="edb4c-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="edb4c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="edb4c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="edb4c-105">A adjointable és a mérést követően a rendszer a `Zero` megadott számú próbaverzió elvégzésével megbecsüli a gyakoriságot, amellyel a mérték sikeres (visszaadott) értékkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="edb4c-105">Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.</span></span>

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="edb4c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="edb4c-106">Input</span></span>

### <a name="preparation--qubit--unit-adj"></a><span data-ttu-id="edb4c-107">előkészítés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj</span><span class="sxs-lookup"><span data-stu-id="edb4c-107">preparation : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="edb4c-108">Egy adjointable művelet $P $, amely előkészít egy adott állapotot $ \rho $ értékre a bemeneti regiszterében.</span><span class="sxs-lookup"><span data-stu-id="edb4c-108">An adjointable operation $P$ that prepares a given state $\rho$ on its input register.</span></span>


### <a name="measurement--qubit--__invalidresult__"></a><span data-ttu-id="edb4c-109">mérték: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="edb4c-109">measurement : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __invalid<Result>__</span></span> 

<span data-ttu-id="edb4c-110">Egy művelet, $M $, amely a kamat mértékét jelképezi.</span><span class="sxs-lookup"><span data-stu-id="edb4c-110">An operation $M$ representing the measurement of interest.</span></span>


### <a name="nqubits--int"></a><span data-ttu-id="edb4c-111">nQubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="edb4c-111">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="edb4c-112">Azon qubits száma, amelyeken az egyes műveletek előkészítése és mérése megtörténjen.</span><span class="sxs-lookup"><span data-stu-id="edb4c-112">The number of qubits on which the preparation and measurement each act.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="edb4c-113">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="edb4c-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="edb4c-114">Ennyi alkalommal kell elvégezni a mérést a kamat gyakoriságának becslése érdekében.</span><span class="sxs-lookup"><span data-stu-id="edb4c-114">The number of times that the measurement should be performed in order to estimate the frequency of interest.</span></span>



## <a name="output--double"></a><span data-ttu-id="edb4c-115">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="edb4c-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="edb4c-116">Az a gyakoriság, amellyel a $M (P (\ket{00 \cdots 0} \bra{00 \cdots 0}) $ értéket adja vissza `Zero` , amely a nem torzítatlan binomiális kalkulátor $ \hat{p} = n \_ {\uparrow}/n \_ {\text{Measurements}} $ \hat{p}, ahol a $n \_ {\uparrow} $ a `Zero` megfigyelt eredmények száma.</span><span class="sxs-lookup"><span data-stu-id="edb4c-116">An estimate $\hat{p}$ of the frequency with which $M(P(\ket{00 \cdots 0}\bra{00 \cdots 0}))$ returns `Zero`, obtained using the unbiased binomial estimator $\hat{p} = n\_{\uparrow} / n\_{\text{measurements}}$, where $n\_{\uparrow}$ is the number of `Zero` results observed.</span></span>

## <a name="remarks"></a><span data-ttu-id="edb4c-117">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="edb4c-117">Remarks</span></span>

<span data-ttu-id="edb4c-118">A adjointable műveletek esetében bizonyos feltételezések olyanok, mint például a művelet meghívása, hogy a qubits pontosan ugyanazt az állapotot hozza létre, ami lehetővé teszi a célszámítógép számára a teljesítmény optimalizálása érdekében.</span><span class="sxs-lookup"><span data-stu-id="edb4c-118">For adjointable operations, certain assumptions can be made such like calling the operation will prepare the qubits to exactly the same state, which allow target machines to make some performance optimizations.</span></span>