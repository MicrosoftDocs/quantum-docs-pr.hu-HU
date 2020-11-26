---
uid: Microsoft.Quantum.Logical.Xor
title: XOR függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: afb94bd1fd0b791a9a7d84bc28b0cc2baf9a0938
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197092"
---
# <a name="xor-function"></a><span data-ttu-id="4d3b3-102">XOR függvény</span><span class="sxs-lookup"><span data-stu-id="4d3b3-102">Xor function</span></span>

<span data-ttu-id="4d3b3-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="4d3b3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="4d3b3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4d3b3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4d3b3-105">Két érték logikai kizárólagos kivonását adja vissza.</span><span class="sxs-lookup"><span data-stu-id="4d3b3-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="4d3b3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4d3b3-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="4d3b3-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4d3b3-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4d3b3-108">Az első megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="4d3b3-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="4d3b3-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4d3b3-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4d3b3-110">A második megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="4d3b3-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="4d3b3-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="4d3b3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="4d3b3-112">`true` Ha és csak akkor, ha pontosan az egyik a `a` és `b` a `true` .</span><span class="sxs-lookup"><span data-stu-id="4d3b3-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>