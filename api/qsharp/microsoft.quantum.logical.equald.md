---
uid: Microsoft.Quantum.Logical.EqualD
title: Egyenrangú függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualD
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: d6731b293ba402f5cd43591d3c2bcd258e8ebe32
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198146"
---
# <a name="equald-function"></a><span data-ttu-id="df02c-102">Egyenrangú függvény</span><span class="sxs-lookup"><span data-stu-id="df02c-102">EqualD function</span></span>

<span data-ttu-id="df02c-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="df02c-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="df02c-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="df02c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="df02c-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet egyenlő.</span><span class="sxs-lookup"><span data-stu-id="df02c-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="df02c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="df02c-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="df02c-107">a: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="df02c-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="df02c-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="df02c-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="df02c-109">b: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="df02c-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="df02c-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="df02c-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="df02c-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="df02c-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="df02c-112">`true` Ha és csak akkor, ha `a` egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="df02c-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="df02c-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="df02c-113">Remarks</span></span>

<span data-ttu-id="df02c-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="df02c-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualD(a, b);
```