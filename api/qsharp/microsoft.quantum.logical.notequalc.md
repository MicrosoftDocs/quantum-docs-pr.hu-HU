---
uid: Microsoft.Quantum.Logical.NotEqualC
title: NotEqualC függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualC
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: b26ad3515cb801b122858b9474aea76a0e5c498b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709819"
---
# <a name="notequalc-function"></a><span data-ttu-id="a40c2-102">NotEqualC függvény</span><span class="sxs-lookup"><span data-stu-id="a40c2-102">NotEqualC function</span></span>

<span data-ttu-id="a40c2-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="a40c2-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="a40c2-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a40c2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a40c2-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet nem egyenlő.</span><span class="sxs-lookup"><span data-stu-id="a40c2-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="a40c2-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="a40c2-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="a40c2-107">a: [összetett](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="a40c2-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="a40c2-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="a40c2-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="a40c2-109">b: [összetett](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="a40c2-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="a40c2-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="a40c2-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="a40c2-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a40c2-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a40c2-112">`true` Ha és csak akkor, ha `a` nem egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="a40c2-112">`true` if and only if `a` is not equal to `b`.</span></span>