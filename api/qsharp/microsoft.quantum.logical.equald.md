---
uid: Microsoft.Quantum.Logical.EqualD
title: Egyenrangú függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: f8a24d7bfb9b4f7b8b0e1f68a94bfb341716b024
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98816867"
---
# <a name="equald-function"></a><span data-ttu-id="5e051-102">Egyenrangú függvény</span><span class="sxs-lookup"><span data-stu-id="5e051-102">EqualD function</span></span>

<span data-ttu-id="5e051-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5e051-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5e051-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5e051-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5e051-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="5e051-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="5e051-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="5e051-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="5e051-107">a: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5e051-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5e051-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="5e051-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="5e051-109">b: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5e051-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5e051-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="5e051-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5e051-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="5e051-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5e051-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="5e051-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5e051-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="5e051-113">Remarks</span></span>

<span data-ttu-id="5e051-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="5e051-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualD(a, b);
```