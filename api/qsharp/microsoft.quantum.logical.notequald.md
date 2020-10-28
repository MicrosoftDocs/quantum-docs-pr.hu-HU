---
uid: Microsoft.Quantum.Logical.NotEqualD
title: NotEqualD függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualD
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: dd21fcc1d0d73bd210303bfbf4f336386b912107
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723473"
---
# <a name="notequald-function"></a><span data-ttu-id="ccfd6-102">NotEqualD függvény</span><span class="sxs-lookup"><span data-stu-id="ccfd6-102">NotEqualD function</span></span>

<span data-ttu-id="ccfd6-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="ccfd6-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="ccfd6-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ccfd6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ccfd6-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet nem egyenlő.</span><span class="sxs-lookup"><span data-stu-id="ccfd6-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="ccfd6-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ccfd6-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="ccfd6-107">a: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ccfd6-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ccfd6-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="ccfd6-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="ccfd6-109">b: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ccfd6-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ccfd6-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="ccfd6-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="ccfd6-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="ccfd6-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ccfd6-112">`true` Ha és csak akkor, ha `a` nem egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="ccfd6-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ccfd6-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="ccfd6-113">Remarks</span></span>

<span data-ttu-id="ccfd6-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="ccfd6-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualD(a, b);
```