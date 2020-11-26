---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196412"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="d5b3a-102">FeatureRegisterSize függvény</span><span class="sxs-lookup"><span data-stu-id="d5b3a-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="d5b3a-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d5b3a-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d5b3a-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d5b3a-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="d5b3a-105">Egy adott szolgáltatás vektorának kódolásához szükséges qubits számát adja vissza.</span><span class="sxs-lookup"><span data-stu-id="d5b3a-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="d5b3a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d5b3a-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="d5b3a-107">minta: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d5b3a-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d5b3a-108">Egy qubit-regiszterbe kódolható minta-szolgáltatás vektora.</span><span class="sxs-lookup"><span data-stu-id="d5b3a-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="d5b3a-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d5b3a-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d5b3a-110">A qubit-regiszterbe való kódoláshoz szükséges méret `sample` , a qubits számában kifejezve.</span><span class="sxs-lookup"><span data-stu-id="d5b3a-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>