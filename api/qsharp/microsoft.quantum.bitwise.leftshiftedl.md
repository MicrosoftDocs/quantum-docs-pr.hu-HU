---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 17e5c845755f74e9703381bc82bfd63be836d038
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718636"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="bc966-102">LeftShiftedL függvény</span><span class="sxs-lookup"><span data-stu-id="bc966-102">LeftShiftedL function</span></span>

<span data-ttu-id="bc966-103">Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="bc966-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="bc966-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc966-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bc966-105">Egy adott számú biten hagyott szám bitenkénti-ábrázolását tolja át.</span><span class="sxs-lookup"><span data-stu-id="bc966-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="bc966-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bc966-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="bc966-107">érték: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bc966-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bc966-108">Az a szám, amelynek a bitenkénti-ábrázolását balra kell átirányítani (jelentősebb).</span><span class="sxs-lookup"><span data-stu-id="bc966-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="bc966-109">összeg: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bc966-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bc966-110">Azon bitek száma, amelyekről `value` balra kell váltani.</span><span class="sxs-lookup"><span data-stu-id="bc966-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="bc966-111">Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bc966-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="bc966-112">A érték a `value` `amount` biten balra tolódott.</span><span class="sxs-lookup"><span data-stu-id="bc966-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="bc966-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="bc966-113">Remarks</span></span>

<span data-ttu-id="bc966-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="bc966-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```