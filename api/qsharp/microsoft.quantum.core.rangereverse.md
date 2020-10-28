---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713234"
---
# <a name="rangereverse-function"></a><span data-ttu-id="54cab-102">RangeReverse függvény</span><span class="sxs-lookup"><span data-stu-id="54cab-102">RangeReverse function</span></span>

<span data-ttu-id="54cab-103">Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="54cab-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="54cab-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="54cab-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="54cab-105">Egy új tartományt ad vissza, amely a bemeneti tartomány fordított értéke.</span><span class="sxs-lookup"><span data-stu-id="54cab-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="54cab-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="54cab-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="54cab-107">r: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="54cab-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="54cab-108">Bemeneti tartomány.</span><span class="sxs-lookup"><span data-stu-id="54cab-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="54cab-109">Kimenet: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="54cab-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="54cab-110">Egy új tartomány, amely a megadott tartomány fordítottja.</span><span class="sxs-lookup"><span data-stu-id="54cab-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="54cab-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="54cab-111">Remarks</span></span>

<span data-ttu-id="54cab-112">Vegye figyelembe, hogy a tartomány fordított értéke nem egyszerűen `end` .. `-step` . `start` , mert a tartomány tényleges utolsó eleme nem egyezhet meg `end` .</span><span class="sxs-lookup"><span data-stu-id="54cab-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>