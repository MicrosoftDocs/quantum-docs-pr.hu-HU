---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 8cd274d5e299df2f556006baf7457d54aebcd071
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723487"
---
# <a name="lessthand-function"></a><span data-ttu-id="f6250-102">LessThanD függvény</span><span class="sxs-lookup"><span data-stu-id="f6250-102">LessThanD function</span></span>

<span data-ttu-id="f6250-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f6250-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f6250-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f6250-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f6250-105">Igaz értéket ad vissza, és csak akkor, ha egy szám kisebb, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="f6250-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="f6250-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f6250-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="f6250-107">a: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f6250-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f6250-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="f6250-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="f6250-109">b: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f6250-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f6250-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="f6250-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f6250-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="f6250-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f6250-112">`true` Ha és csak akkor, ha `a` a értéke szigorúan kisebb `b` .</span><span class="sxs-lookup"><span data-stu-id="f6250-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f6250-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="f6250-113">Remarks</span></span>

<span data-ttu-id="f6250-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="f6250-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanD(a, b);
```