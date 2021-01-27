---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: DrawRandomBool művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853693"
---
# <a name="drawrandombool-operation"></a><span data-ttu-id="48532-102">DrawRandomBool művelet</span><span class="sxs-lookup"><span data-stu-id="48532-102">DrawRandomBool operation</span></span>

<span data-ttu-id="48532-103">Névtér: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="48532-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="48532-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="48532-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="48532-105">A siker valószínűsége miatt egyetlen Bernoulli-próbaverziót ad vissza, amely igaz a megadott valószínűséggel.</span><span class="sxs-lookup"><span data-stu-id="48532-105">Given a success probability, returns a single Bernoulli trial that is true with the given probability.</span></span>

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="48532-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="48532-106">Input</span></span>

### <a name="successprobability--double"></a><span data-ttu-id="48532-107">successProbability: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="48532-107">successProbability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="48532-108">Az a valószínűség, amellyel `true` vissza kell adni.</span><span class="sxs-lookup"><span data-stu-id="48532-108">The probability with which `true` should be returned.</span></span>



## <a name="output--bool"></a><span data-ttu-id="48532-109">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="48532-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="48532-110">`true` a valószínűséggel `successProbability` és `false` a valószínűséggel `1.0 - successProbability` .</span><span class="sxs-lookup"><span data-stu-id="48532-110">`true` with probability `successProbability` and `false` with probability `1.0 - successProbability`.</span></span>

## <a name="example"></a><span data-ttu-id="48532-111">Példa</span><span class="sxs-lookup"><span data-stu-id="48532-111">Example</span></span>

<span data-ttu-id="48532-112">A következő Q # kódrészlet minták egy elfogult érmeből állnak a tükrözésre:</span><span class="sxs-lookup"><span data-stu-id="48532-112">The following Q# snippet samples flips from a biased coin:</span></span>

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```