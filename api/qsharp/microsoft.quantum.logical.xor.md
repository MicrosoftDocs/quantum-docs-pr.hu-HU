---
uid: Microsoft.Quantum.Logical.Xor
title: XOR függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Xor
qsharp.summary: Returns the Boolean exclusive disjunction of two values.
ms.openlocfilehash: 4a4af7f628ca64170e046584d9caffe7ceee3d56
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848457"
---
# <a name="xor-function"></a><span data-ttu-id="38a2e-102">XOR függvény</span><span class="sxs-lookup"><span data-stu-id="38a2e-102">Xor function</span></span>

<span data-ttu-id="38a2e-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="38a2e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="38a2e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="38a2e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="38a2e-105">Két érték logikai kizárólagos kivonását adja vissza.</span><span class="sxs-lookup"><span data-stu-id="38a2e-105">Returns the Boolean exclusive disjunction of two values.</span></span>

```qsharp
function Xor (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="38a2e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="38a2e-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="38a2e-107">a: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="38a2e-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="38a2e-108">Az első megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="38a2e-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="38a2e-109">b: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="38a2e-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="38a2e-110">A második megfontolandó érték.</span><span class="sxs-lookup"><span data-stu-id="38a2e-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="38a2e-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="38a2e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="38a2e-112">`true` Ha és csak akkor, ha pontosan az egyik a `a` és `b` a `true` .</span><span class="sxs-lookup"><span data-stu-id="38a2e-112">`true` if and only if exactly one of `a` and `b` is `true`.</span></span>