---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 7135ed4b3414d143f5020496ae524bf89980a8a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849159"
---
# <a name="lessthand-function"></a><span data-ttu-id="17d04-102">LessThanD függvény</span><span class="sxs-lookup"><span data-stu-id="17d04-102">LessThanD function</span></span>

<span data-ttu-id="17d04-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="17d04-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="17d04-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="17d04-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="17d04-105">Igaz értéket ad vissza, és csak akkor, ha egy szám kisebb, mint egy másik szám.</span><span class="sxs-lookup"><span data-stu-id="17d04-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="17d04-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="17d04-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="17d04-107">a: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="17d04-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="17d04-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="17d04-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="17d04-109">b: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="17d04-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="17d04-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="17d04-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="17d04-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="17d04-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="17d04-112">`true` Ha és csak akkor, ha `a` a értéke szigorúan kisebb `b` .</span><span class="sxs-lookup"><span data-stu-id="17d04-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="17d04-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="17d04-113">Remarks</span></span>

<span data-ttu-id="17d04-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="17d04-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanD(a, b);
```