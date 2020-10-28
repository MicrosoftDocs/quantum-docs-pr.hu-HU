---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b0ca7d3cb84c58429e9b3a29893a6140a717006b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718577"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="b855d-102">RightShiftedI függvény</span><span class="sxs-lookup"><span data-stu-id="b855d-102">RightShiftedI function</span></span>

<span data-ttu-id="b855d-103">Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="b855d-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="b855d-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b855d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b855d-105">Egy szám bitenkénti-ábrázolását egy adott számú biten keresztül tolja.</span><span class="sxs-lookup"><span data-stu-id="b855d-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="b855d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b855d-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="b855d-107">érték: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b855d-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b855d-108">Az a szám, amelynek a bitenkénti-ábrázolását jobbra (kevésbé jelentős) kell átirányítani.</span><span class="sxs-lookup"><span data-stu-id="b855d-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="b855d-109">összeg: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b855d-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b855d-110">Azon bitek száma, amelyeknek `value` jobbra kell váltania.</span><span class="sxs-lookup"><span data-stu-id="b855d-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="b855d-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b855d-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b855d-112">A, a `value` bitek által jobbra eltolt érték `amount` .</span><span class="sxs-lookup"><span data-stu-id="b855d-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="b855d-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b855d-113">Remarks</span></span>

<span data-ttu-id="b855d-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="b855d-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```