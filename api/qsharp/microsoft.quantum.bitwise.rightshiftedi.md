---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b20a4a8c281a470af9a4828f8a5ca905a7918723
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209774"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="f2325-102">RightShiftedI függvény</span><span class="sxs-lookup"><span data-stu-id="f2325-102">RightShiftedI function</span></span>

<span data-ttu-id="f2325-103">Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="f2325-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="f2325-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2325-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2325-105">Egy szám bitenkénti-ábrázolását egy adott számú biten keresztül tolja.</span><span class="sxs-lookup"><span data-stu-id="f2325-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="f2325-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f2325-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="f2325-107">érték: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f2325-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f2325-108">Az a szám, amelynek a bitenkénti-ábrázolását jobbra (kevésbé jelentős) kell átirányítani.</span><span class="sxs-lookup"><span data-stu-id="f2325-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="f2325-109">összeg: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f2325-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f2325-110">Azon bitek száma, amelyeknek `value` jobbra kell váltania.</span><span class="sxs-lookup"><span data-stu-id="f2325-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="f2325-111">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f2325-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f2325-112">A, a `value` bitek által jobbra eltolt érték `amount` .</span><span class="sxs-lookup"><span data-stu-id="f2325-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="f2325-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="f2325-113">Remarks</span></span>

<span data-ttu-id="f2325-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="f2325-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```