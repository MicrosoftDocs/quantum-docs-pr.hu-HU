---
uid: Microsoft.Quantum.MachineLearning.NQubitsRequired
title: NQubitsRequired függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NQubitsRequired
qsharp.summary: Returns the number of qubits required to apply a given sequential classifier.
ms.openlocfilehash: 8f6c1bf3dfef3152a6ba8eada0980d6940724259
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854967"
---
# <a name="nqubitsrequired-function"></a><span data-ttu-id="faac8-102">NQubitsRequired függvény</span><span class="sxs-lookup"><span data-stu-id="faac8-102">NQubitsRequired function</span></span>

<span data-ttu-id="faac8-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="faac8-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="faac8-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="faac8-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="faac8-105">Egy adott szekvenciális osztályozó alkalmazásához szükséges qubits számát adja vissza.</span><span class="sxs-lookup"><span data-stu-id="faac8-105">Returns the number of qubits required to apply a given sequential classifier.</span></span>

```qsharp
function NQubitsRequired (model : Microsoft.Quantum.MachineLearning.SequentialModel) : Int
```


## <a name="input"></a><span data-ttu-id="faac8-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="faac8-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="faac8-107">modell: [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="faac8-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>





## <a name="output--int"></a><span data-ttu-id="faac8-108">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="faac8-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="faac8-109">Azon regiszter minimális mérete, amelyen a szekvenciális osztályozó alkalmazható.</span><span class="sxs-lookup"><span data-stu-id="faac8-109">The minimum size of a register on which the sequential classifier may be applied.</span></span>