---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: ce68311adf211169c2fb499bb189332370a6d6ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718661"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="de574-102">LeftShiftedI függvény</span><span class="sxs-lookup"><span data-stu-id="de574-102">LeftShiftedI function</span></span>

<span data-ttu-id="de574-103">Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="de574-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="de574-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="de574-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="de574-105">Egy adott számú biten hagyott szám bitenkénti-ábrázolását tolja át.</span><span class="sxs-lookup"><span data-stu-id="de574-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="de574-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="de574-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="de574-107">érték: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="de574-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="de574-108">Az a szám, amelynek a bitenkénti-ábrázolását balra kell átirányítani (jelentősebb).</span><span class="sxs-lookup"><span data-stu-id="de574-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="de574-109">összeg: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="de574-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="de574-110">Azon bitek száma, amelyekről `value` balra kell váltani.</span><span class="sxs-lookup"><span data-stu-id="de574-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="de574-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="de574-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="de574-112">A érték a `value` `amount` biten balra tolódott.</span><span class="sxs-lookup"><span data-stu-id="de574-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="de574-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="de574-113">Remarks</span></span>

<span data-ttu-id="de574-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="de574-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```