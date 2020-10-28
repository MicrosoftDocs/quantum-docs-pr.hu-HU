---
uid: Microsoft.Quantum.Logical.Xor
title: XOR függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: ae43545e19e81ed5da17c3d58c62ac0b7ee765f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723291"
---
# <a name="xor-function"></a><span data-ttu-id="306cd-102">XOR függvény</span><span class="sxs-lookup"><span data-stu-id="306cd-102">Xor function</span></span>

<span data-ttu-id="306cd-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="306cd-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="306cd-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="306cd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="306cd-105">Két érték logikai kizárólagos kivonását adja vissza.</span><span class="sxs-lookup"><span data-stu-id="306cd-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="306cd-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="306cd-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="306cd-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="306cd-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="306cd-108">Az első megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="306cd-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="306cd-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="306cd-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="306cd-110">A második megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="306cd-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="306cd-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="306cd-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="306cd-112">`true` Ha és csak akkor, ha pontosan az egyik a `a` és `b` a `true` .</span><span class="sxs-lookup"><span data-stu-id="306cd-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>