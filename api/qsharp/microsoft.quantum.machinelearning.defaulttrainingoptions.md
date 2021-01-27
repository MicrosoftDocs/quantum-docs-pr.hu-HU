---
uid: Microsoft.Quantum.MachineLearning.DefaultTrainingOptions
title: DefaultTrainingOptions függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: DefaultTrainingOptions
qsharp.summary: Returns a default set of options for training classifiers.
ms.openlocfilehash: 474683ce5b9ec22bec686fb29d87728afe24d23a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855994"
---
# <a name="defaulttrainingoptions-function"></a><span data-ttu-id="dbce6-102">DefaultTrainingOptions függvény</span><span class="sxs-lookup"><span data-stu-id="dbce6-102">DefaultTrainingOptions function</span></span>

<span data-ttu-id="dbce6-103">Névtér: [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="dbce6-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="dbce6-104">Csomag: [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="dbce6-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="dbce6-105">Az osztályozók betanítási beállításainak alapértelmezett készletét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="dbce6-105">Returns a default set of options for training classifiers.</span></span>

```qsharp
function DefaultTrainingOptions () : Microsoft.Quantum.MachineLearning.TrainingOptions
```


## <a name="output--trainingoptions"></a><span data-ttu-id="dbce6-106">Kimenet: [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="dbce6-106">Output : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="dbce6-107">Az osztályozók betanításakor használható alapértelmezett képzési lehetőségek ésszerű készlete.</span><span class="sxs-lookup"><span data-stu-id="dbce6-107">A reasonable set of default training options for use when training classifiers.</span></span>

## <a name="example"></a><span data-ttu-id="dbce6-108">Példa</span><span class="sxs-lookup"><span data-stu-id="dbce6-108">Example</span></span>

<span data-ttu-id="dbce6-109">Az alapértelmezett beállítások használatához, de további mérések esetén használja az `w/` operátort:</span><span class="sxs-lookup"><span data-stu-id="dbce6-109">To use the default options, but with additional measurements, use the `w/` operator:</span></span>

```qsharp
let options = DefaultTrainingOptions()
    w/ NMeasurements <- 1000000;
```