---
uid: Microsoft.Quantum.Logical.NotEqualCP
title: NotEqualCP függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualCP
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 81dd998353f674d55afe85dd20904047391bdb40
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720737"
---
# <a name="notequalcp-function"></a><span data-ttu-id="8b57c-102">NotEqualCP függvény</span><span class="sxs-lookup"><span data-stu-id="8b57c-102">NotEqualCP function</span></span>

<span data-ttu-id="8b57c-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="8b57c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="8b57c-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8b57c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8b57c-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet nem egyenlő.</span><span class="sxs-lookup"><span data-stu-id="8b57c-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="8b57c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8b57c-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="8b57c-107">a: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="8b57c-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="8b57c-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="8b57c-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="8b57c-109">b: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="8b57c-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="8b57c-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="8b57c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="8b57c-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="8b57c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="8b57c-112">`true` Ha és csak akkor, ha `a` nem egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="8b57c-112">`true` if and only if `a` is not equal to `b`.</span></span>