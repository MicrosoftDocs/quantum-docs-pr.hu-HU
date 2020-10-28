---
uid: Microsoft.Quantum.Logical.EqualD
title: Egyenrangú függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 024ddee785a6a907b4a39d0eccc5990b4c5d5d83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92711400"
---
# <a name="equald-function"></a><span data-ttu-id="360c8-102">Egyenrangú függvény</span><span class="sxs-lookup"><span data-stu-id="360c8-102">EqualD function</span></span>

<span data-ttu-id="360c8-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="360c8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="360c8-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="360c8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="360c8-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="360c8-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="360c8-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="360c8-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="360c8-107">a: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="360c8-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="360c8-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="360c8-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="360c8-109">b: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="360c8-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="360c8-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="360c8-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="360c8-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="360c8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="360c8-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="360c8-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="360c8-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="360c8-113">Remarks</span></span>

<span data-ttu-id="360c8-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="360c8-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```