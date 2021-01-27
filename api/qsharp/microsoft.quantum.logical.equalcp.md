---
uid: Microsoft.Quantum.Logical.EqualCP
title: EqualCP függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualCP
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 83bf5ba245038ad1c7c6ed4e8cdb493317276e6a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817161"
---
# <a name="equalcp-function"></a><span data-ttu-id="4ff28-102">EqualCP függvény</span><span class="sxs-lookup"><span data-stu-id="4ff28-102">EqualCP function</span></span>

<span data-ttu-id="4ff28-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4ff28-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4ff28-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4ff28-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4ff28-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="4ff28-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="4ff28-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4ff28-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="4ff28-107">a: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="4ff28-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="4ff28-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="4ff28-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="4ff28-109">b: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="4ff28-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="4ff28-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="4ff28-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4ff28-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4ff28-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4ff28-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="4ff28-112">`true` if and only if `a` is equal to `b`.</span></span>