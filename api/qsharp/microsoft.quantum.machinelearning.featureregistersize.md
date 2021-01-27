---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 2754e901d74175c1841a38d795f5de02dabc9b8d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848427"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="07a94-102">FeatureRegisterSize függvény</span><span class="sxs-lookup"><span data-stu-id="07a94-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="07a94-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="07a94-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="07a94-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="07a94-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="07a94-105">Egy adott szolgáltatás vektorának kódolásához szükséges qubits számát adja vissza.</span><span class="sxs-lookup"><span data-stu-id="07a94-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="07a94-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="07a94-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="07a94-107">minta: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="07a94-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="07a94-108">Egy qubit-regiszterbe kódolható minta-szolgáltatás vektora.</span><span class="sxs-lookup"><span data-stu-id="07a94-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="07a94-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="07a94-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="07a94-110">A qubit-regiszterbe való kódoláshoz szükséges méret `sample` , a qubits számában kifejezve.</span><span class="sxs-lookup"><span data-stu-id="07a94-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>