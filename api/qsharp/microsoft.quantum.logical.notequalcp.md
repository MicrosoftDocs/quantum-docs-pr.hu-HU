---
uid: Microsoft.Quantum.Logical.NotEqualCP
title: NotEqualCP függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualCP
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 85225109a3822a9b63a231631f3d7265143418b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814403"
---
# <a name="notequalcp-function"></a><span data-ttu-id="a5f8e-102">NotEqualCP függvény</span><span class="sxs-lookup"><span data-stu-id="a5f8e-102">NotEqualCP function</span></span>

<span data-ttu-id="a5f8e-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a5f8e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a5f8e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a5f8e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a5f8e-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet nem egyenlő.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualCP (a : Microsoft.Quantum.Math.ComplexPolar, b : Microsoft.Quantum.Math.ComplexPolar) : Bool
```


## <a name="input"></a><span data-ttu-id="a5f8e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a5f8e-106">Input</span></span>

### <a name="a--complexpolar"></a><span data-ttu-id="a5f8e-107">a: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="a5f8e-107">a : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="a5f8e-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-108">The first value to be compared.</span></span>


### <a name="b--complexpolar"></a><span data-ttu-id="a5f8e-109">b: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="a5f8e-109">b : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="a5f8e-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="a5f8e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a5f8e-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a5f8e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a5f8e-112">`true` Ha és csak akkor, ha `a` nem egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="a5f8e-112">`true` if and only if `a` is not equal to `b`.</span></span>