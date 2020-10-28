---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: f8e4c42330f2d6afdc1c0a9bdde36081ccab2f94
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713164"
---
# <a name="rangestep-function"></a><span data-ttu-id="82ca0-102">RangeStep függvény</span><span class="sxs-lookup"><span data-stu-id="82ca0-102">RangeStep function</span></span>

<span data-ttu-id="82ca0-103">Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="82ca0-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="82ca0-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="82ca0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="82ca0-105">Azt az egész számot adja vissza, amely megadja egy tartomány következő értékének kiszámítását.</span><span class="sxs-lookup"><span data-stu-id="82ca0-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="82ca0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="82ca0-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="82ca0-107">tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="82ca0-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="82ca0-108">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="82ca0-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="82ca0-109">A megadott tartomány megadott lépésének értéke.</span><span class="sxs-lookup"><span data-stu-id="82ca0-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="82ca0-110">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="82ca0-110">Remarks</span></span>

<span data-ttu-id="82ca0-111">A Range kifejezés első eleme a `start` , a második elem `start+step` , a harmadik elem `start+step+step` stb., amíg át nem `end` telik.</span><span class="sxs-lookup"><span data-stu-id="82ca0-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>