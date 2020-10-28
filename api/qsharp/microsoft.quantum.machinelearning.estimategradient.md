---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: f42cc30c98346a25f584d7527227a95cb413c32b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719969"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="31ac7-102">EstimateGradient művelet</span><span class="sxs-lookup"><span data-stu-id="31ac7-102">EstimateGradient operation</span></span>

<span data-ttu-id="31ac7-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="31ac7-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="31ac7-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="31ac7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="31ac7-105">Egy adott modellen belül egy szekvenciális osztályozó, egy adott kódolt bemenet esetében pedig a betanítási átmenetet becsüli meg.</span><span class="sxs-lookup"><span data-stu-id="31ac7-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="31ac7-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="31ac7-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="31ac7-107">modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="31ac7-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="31ac7-108">Az a szekvenciális modell, amelynek gradiensét meg kell becsülni.</span><span class="sxs-lookup"><span data-stu-id="31ac7-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="31ac7-109">encodedInput: [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="31ac7-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="31ac7-110">A szekvenciális osztályozó bemenete, amely egy állapot-előkészítési műveletbe van kódolva.</span><span class="sxs-lookup"><span data-stu-id="31ac7-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="31ac7-111">nMeasurements: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="31ac7-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="31ac7-112">A színátmenet becsléséhez használni kívánt mérések száma.</span><span class="sxs-lookup"><span data-stu-id="31ac7-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="31ac7-113">Kimenet: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="31ac7-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="31ac7-114">A betanítási és a modell paramétereinek a betanítási átmenetének becslése.</span><span class="sxs-lookup"><span data-stu-id="31ac7-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="31ac7-115">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="31ac7-115">Remarks</span></span>

<span data-ttu-id="31ac7-116">Ez a művelet egy Hadamard tesztet és a paraméter-eltolási technikát használja együtt a színátmenet becsléséhez.</span><span class="sxs-lookup"><span data-stu-id="31ac7-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>