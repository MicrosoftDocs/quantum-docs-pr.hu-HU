---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: dbe0836af5aa19f1bdce3cfe93be6833358c22be
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192961"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="aea96-102">DrawRandomBool művelet</span><span class="sxs-lookup"><span data-stu-id="aea96-102">DrawRandomBool operation</span></span>

<span data-ttu-id="aea96-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="aea96-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="aea96-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="aea96-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="aea96-105">A siker valószínűsége miatt egyetlen Bernoulli-próbaverziót ad vissza, amely igaz a megadott valószínűséggel.</span><span class="sxs-lookup"><span data-stu-id="aea96-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="aea96-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="aea96-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="aea96-107">successProbability: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="aea96-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="aea96-108">Az a valószínűség, amellyel `true` vissza kell adni.</span><span class="sxs-lookup"><span data-stu-id="aea96-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="aea96-109">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="aea96-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="aea96-110">`true` a valószínűséggel `successProbability` és `false` a valószínűséggel `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="aea96-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>