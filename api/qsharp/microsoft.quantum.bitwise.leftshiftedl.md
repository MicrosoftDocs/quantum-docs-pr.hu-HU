---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 014653011574d0fabb4b9aa04cedf58b87ddf798
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842141"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="d5260-102">LeftShiftedL függvény</span><span class="sxs-lookup"><span data-stu-id="d5260-102">LeftShiftedL function</span></span>

<span data-ttu-id="d5260-103">Névtér: [Microsoft. Quantum. bitenkénti](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="d5260-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="d5260-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d5260-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d5260-105">Egy adott számú biten hagyott szám bitenkénti-ábrázolását tolja át.</span><span class="sxs-lookup"><span data-stu-id="d5260-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="d5260-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="d5260-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="d5260-107">érték: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d5260-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d5260-108">Az a szám, amelynek a bitenkénti-ábrázolását balra kell átirányítani (jelentősebb).</span><span class="sxs-lookup"><span data-stu-id="d5260-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="d5260-109">összeg: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d5260-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d5260-110">Azon bitek száma, amelyekről `value` balra kell váltani.</span><span class="sxs-lookup"><span data-stu-id="d5260-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="d5260-111">Kimenet: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="d5260-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="d5260-112">A érték a `value` `amount` biten balra tolódott.</span><span class="sxs-lookup"><span data-stu-id="d5260-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="d5260-113">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="d5260-113">Remarks</span></span>

<span data-ttu-id="d5260-114">A következők egyenértékűek:</span><span class="sxs-lookup"><span data-stu-id="d5260-114">The following are equivalent:</span></span>

```qsharp
let c = a <<< b;
let c = LeftShiftedL(a, b);
```