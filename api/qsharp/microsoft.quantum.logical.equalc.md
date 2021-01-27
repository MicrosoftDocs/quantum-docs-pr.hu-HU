---
uid: Microsoft.Quantum.Logical.EqualC
title: EqualC függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualC
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 829af5424432b89adeae5243e6caac6a02f3e384
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817247"
---
# <a name="equalc-function"></a><span data-ttu-id="47a43-102">EqualC függvény</span><span class="sxs-lookup"><span data-stu-id="47a43-102">EqualC function</span></span>

<span data-ttu-id="47a43-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="47a43-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="47a43-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="47a43-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="47a43-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="47a43-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualC (a : Microsoft.Quantum.Math.Complex, b : Microsoft.Quantum.Math.Complex) : Bool
```


## <a name="input"></a><span data-ttu-id="47a43-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="47a43-106">Input</span></span>

### <a name="a--complex"></a><span data-ttu-id="47a43-107">a: [összetett](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="47a43-107">a : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="47a43-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="47a43-108">The first value to be compared.</span></span>


### <a name="b--complex"></a><span data-ttu-id="47a43-109">b: [összetett](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="47a43-109">b : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="47a43-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="47a43-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="47a43-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="47a43-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="47a43-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="47a43-112">`true` if and only if `a` is equal to `b`.</span></span>