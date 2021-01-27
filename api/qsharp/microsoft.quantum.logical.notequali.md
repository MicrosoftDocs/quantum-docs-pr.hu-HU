---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: f88ae08f45c284f65151419c214705c74c3fadac
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814509"
---
# <a name="notequali-function"></a><span data-ttu-id="15bce-102">NotEqualI függvény</span><span class="sxs-lookup"><span data-stu-id="15bce-102">NotEqualI function</span></span>

<span data-ttu-id="15bce-103">Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="15bce-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="15bce-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="15bce-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="15bce-105">Igaz értéket ad vissza, és csak akkor, ha két bemenet nem egyenlő.</span><span class="sxs-lookup"><span data-stu-id="15bce-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="15bce-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="15bce-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="15bce-107">a: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="15bce-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="15bce-108">Az összehasonlításhoz használandó első érték.</span><span class="sxs-lookup"><span data-stu-id="15bce-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="15bce-109">b: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="15bce-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="15bce-110">Az összehasonlítandó második érték.</span><span class="sxs-lookup"><span data-stu-id="15bce-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="15bce-111">Kimenet: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="15bce-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="15bce-112">`true` Ha és csak akkor, ha `a` nem egyenlő `b` .</span><span class="sxs-lookup"><span data-stu-id="15bce-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="15bce-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="15bce-113">Remarks</span></span>

<span data-ttu-id="15bce-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="15bce-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualI(a, b);
```