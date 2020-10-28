---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720280"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="b2d5f-102">DrawRandomBool művelet</span><span class="sxs-lookup"><span data-stu-id="b2d5f-102">DrawRandomBool operation</span></span>

<span data-ttu-id="b2d5f-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="b2d5f-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="b2d5f-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b2d5f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b2d5f-105">A siker valószínűsége miatt egyetlen Bernoulli-próbaverziót ad vissza, amely igaz a megadott valószínűséggel.</span><span class="sxs-lookup"><span data-stu-id="b2d5f-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="b2d5f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b2d5f-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="b2d5f-107">successProbability: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b2d5f-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b2d5f-108">Az a valószínűség, amellyel `true` vissza kell adni.</span><span class="sxs-lookup"><span data-stu-id="b2d5f-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b2d5f-109">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="b2d5f-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b2d5f-110">`true` a valószínűséggel `successProbability` és `false` a valószínűséggel `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="b2d5f-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>