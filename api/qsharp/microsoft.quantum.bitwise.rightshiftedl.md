---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 3d941e1a0bcd96fe54ab01019293d883f11547a1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219515"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="753b5-102">RightShiftedL függvény</span><span class="sxs-lookup"><span data-stu-id="753b5-102">RightShiftedL function</span></span>

<span data-ttu-id="753b5-103">Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="753b5-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="753b5-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="753b5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="753b5-105">Egy szám bitenkénti-ábrázolását egy adott számú biten keresztül tolja.</span><span class="sxs-lookup"><span data-stu-id="753b5-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="753b5-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="753b5-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="753b5-107">érték: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="753b5-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="753b5-108">Az a szám, amelynek a bitenkénti-ábrázolását jobbra (kevésbé jelentős) kell átirányítani.</span><span class="sxs-lookup"><span data-stu-id="753b5-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="753b5-109">összeg: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="753b5-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="753b5-110">Azon bitek száma, amelyeknek `value` jobbra kell váltania.</span><span class="sxs-lookup"><span data-stu-id="753b5-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="753b5-111">Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="753b5-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="753b5-112">A, a `value` bitek által jobbra eltolt érték `amount` .</span><span class="sxs-lookup"><span data-stu-id="753b5-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="753b5-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="753b5-113">Remarks</span></span>

<span data-ttu-id="753b5-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="753b5-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```