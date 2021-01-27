---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 38edcb67e7dcc5d2e971fb507a792937774a702c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844385"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="bc3c6-102">EstimateGradient művelet</span><span class="sxs-lookup"><span data-stu-id="bc3c6-102">EstimateGradient operation</span></span>

<span data-ttu-id="bc3c6-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="bc3c6-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="bc3c6-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="bc3c6-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="bc3c6-105">Egy adott modellen belül egy szekvenciális osztályozó, egy adott kódolt bemenet esetében pedig a betanítási átmenetet becsüli meg.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="bc3c6-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bc3c6-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="bc3c6-107">modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="bc3c6-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="bc3c6-108">Az a szekvenciális modell, amelynek gradiensét meg kell becsülni.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="bc3c6-109">encodedInput: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="bc3c6-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="bc3c6-110">A szekvenciális osztályozó bemenete, amely egy állapot-előkészítési műveletbe van kódolva.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="bc3c6-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bc3c6-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bc3c6-112">A színátmenet becsléséhez használni kívánt mérések száma.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="bc3c6-113">Kimenet: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="bc3c6-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="bc3c6-114">A betanítási és a modell paramétereinek a betanítási átmenetének becslése.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="bc3c6-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="bc3c6-115">Remarks</span></span>

<span data-ttu-id="bc3c6-116">Ez a művelet egy Hadamard tesztet és a paraméter-eltolási technikát használja együtt a színátmenet becsléséhez.</span><span class="sxs-lookup"><span data-stu-id="bc3c6-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>