---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3a7220489bfa241e2337df14291bafb1d6e0e19e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209859"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="87da1-102">LeftShiftedI függvény</span><span class="sxs-lookup"><span data-stu-id="87da1-102">LeftShiftedI function</span></span>

<span data-ttu-id="87da1-103">Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="87da1-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="87da1-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="87da1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="87da1-105">Egy adott számú biten hagyott szám bitenkénti-ábrázolását tolja át.</span><span class="sxs-lookup"><span data-stu-id="87da1-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="87da1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="87da1-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="87da1-107">érték: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="87da1-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="87da1-108">Az a szám, amelynek a bitenkénti-ábrázolását balra kell átirányítani (jelentősebb).</span><span class="sxs-lookup"><span data-stu-id="87da1-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="87da1-109">összeg: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="87da1-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="87da1-110">Azon bitek száma, amelyekről `value` balra kell váltani.</span><span class="sxs-lookup"><span data-stu-id="87da1-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="87da1-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="87da1-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="87da1-112">A érték a `value` `amount` biten balra tolódott.</span><span class="sxs-lookup"><span data-stu-id="87da1-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="87da1-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="87da1-113">Remarks</span></span>

<span data-ttu-id="87da1-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="87da1-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```