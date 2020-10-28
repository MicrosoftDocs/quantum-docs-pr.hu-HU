---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 8f7c47c7547e7a0ac1672f308de445c1b46461e1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723290"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="060a9-102">FeatureRegisterSize függvény</span><span class="sxs-lookup"><span data-stu-id="060a9-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="060a9-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="060a9-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="060a9-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="060a9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="060a9-105">Egy adott szolgáltatás vektorának kódolásához szükséges qubits számát adja vissza.</span><span class="sxs-lookup"><span data-stu-id="060a9-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="060a9-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="060a9-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="060a9-107">minta: [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="060a9-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="060a9-108">Egy qubit-regiszterbe kódolható minta-szolgáltatás vektora.</span><span class="sxs-lookup"><span data-stu-id="060a9-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="060a9-109">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="060a9-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="060a9-110">A qubit-regiszterbe való kódoláshoz szükséges méret `sample` , a qubits számában kifejezve.</span><span class="sxs-lookup"><span data-stu-id="060a9-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>