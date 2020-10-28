---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 2929ba58b636847257391930e1019769fd2c2580
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718576"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="fabfe-102">RightShiftedL függvény</span><span class="sxs-lookup"><span data-stu-id="fabfe-102">RightShiftedL function</span></span>

<span data-ttu-id="fabfe-103">Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="fabfe-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="fabfe-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fabfe-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fabfe-105">Egy szám bitenkénti-ábrázolását egy adott számú biten keresztül tolja.</span><span class="sxs-lookup"><span data-stu-id="fabfe-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="fabfe-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fabfe-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="fabfe-107">érték: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fabfe-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fabfe-108">Az a szám, amelynek a bitenkénti-ábrázolását jobbra (kevésbé jelentős) kell átirányítani.</span><span class="sxs-lookup"><span data-stu-id="fabfe-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="fabfe-109">összeg: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fabfe-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fabfe-110">Azon bitek száma, amelyeknek `value` jobbra kell váltania.</span><span class="sxs-lookup"><span data-stu-id="fabfe-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="fabfe-111">Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="fabfe-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="fabfe-112">A, a `value` bitek által jobbra eltolt érték `amount` .</span><span class="sxs-lookup"><span data-stu-id="fabfe-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="fabfe-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="fabfe-113">Remarks</span></span>

<span data-ttu-id="fabfe-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="fabfe-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedL(a, b);
```