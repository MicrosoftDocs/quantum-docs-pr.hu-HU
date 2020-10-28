---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: NearlyEqualD függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: 332f9ea1753b539eba7b931d5b948b2a238d1abf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709874"
---
# <a name="nearlyequald-function"></a><span data-ttu-id="21e38-102">NearlyEqualD függvény</span><span class="sxs-lookup"><span data-stu-id="21e38-102">NearlyEqualD function</span></span>

<span data-ttu-id="21e38-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="21e38-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="21e38-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="21e38-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="21e38-105">Igaz értéket ad vissza, ha két bemenet közel egyenlő (azaz a 1e-12 tűréshatáron belül).</span><span class="sxs-lookup"><span data-stu-id="21e38-105">Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).</span></span>

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="21e38-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="21e38-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="21e38-107">a: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="21e38-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="21e38-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="21e38-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="21e38-109">b: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="21e38-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="21e38-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="21e38-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="21e38-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="21e38-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="21e38-112">`true` Ha és csak akkor, ha `a` majdnem egyenlő a következővel: `b` .</span><span class="sxs-lookup"><span data-stu-id="21e38-112">`true` if and only if `a` is nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="21e38-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="21e38-113">Remarks</span></span>

<span data-ttu-id="21e38-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="21e38-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```