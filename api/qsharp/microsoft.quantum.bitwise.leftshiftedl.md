---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 00d4f9151c620e044074930933ea2912b52534ed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219668"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="698b3-102">LeftShiftedL függvény</span><span class="sxs-lookup"><span data-stu-id="698b3-102">LeftShiftedL function</span></span>

<span data-ttu-id="698b3-103">Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="698b3-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="698b3-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="698b3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="698b3-105">Egy adott számú biten hagyott szám bitenkénti-ábrázolását tolja át.</span><span class="sxs-lookup"><span data-stu-id="698b3-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="698b3-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="698b3-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="698b3-107">érték: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="698b3-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="698b3-108">Az a szám, amelynek a bitenkénti-ábrázolását balra kell átirányítani (jelentősebb).</span><span class="sxs-lookup"><span data-stu-id="698b3-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="698b3-109">összeg: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="698b3-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="698b3-110">Azon bitek száma, amelyekről `value` balra kell váltani.</span><span class="sxs-lookup"><span data-stu-id="698b3-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="698b3-111">Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="698b3-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="698b3-112">A érték a `value` `amount` biten balra tolódott.</span><span class="sxs-lookup"><span data-stu-id="698b3-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="698b3-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="698b3-113">Remarks</span></span>

<span data-ttu-id="698b3-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="698b3-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```