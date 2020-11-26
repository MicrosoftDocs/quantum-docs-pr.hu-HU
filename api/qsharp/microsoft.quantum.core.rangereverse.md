---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213837"
---
# <a name="rangereverse-function"></a><span data-ttu-id="41f2b-102">RangeReverse függvény</span><span class="sxs-lookup"><span data-stu-id="41f2b-102">RangeReverse function</span></span>

<span data-ttu-id="41f2b-103">Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="41f2b-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="41f2b-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="41f2b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="41f2b-105">Egy új tartományt ad vissza, amely a bemeneti tartomány fordított értéke.</span><span class="sxs-lookup"><span data-stu-id="41f2b-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="41f2b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="41f2b-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="41f2b-107">r: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="41f2b-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="41f2b-108">Bemeneti tartomány.</span><span class="sxs-lookup"><span data-stu-id="41f2b-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="41f2b-109">Kimenet: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="41f2b-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="41f2b-110">Egy új tartomány, amely a megadott tartomány fordítottja.</span><span class="sxs-lookup"><span data-stu-id="41f2b-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="41f2b-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="41f2b-111">Remarks</span></span>

<span data-ttu-id="41f2b-112">Vegye figyelembe, hogy a tartomány fordított értéke nem egyszerűen `end` .. `-step` . `start` , mert a tartomány tényleges utolsó eleme nem egyezhet meg `end` .</span><span class="sxs-lookup"><span data-stu-id="41f2b-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>