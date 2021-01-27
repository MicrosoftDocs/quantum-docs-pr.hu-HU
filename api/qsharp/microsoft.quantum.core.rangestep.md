---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 667b579337eec28d6b75de61668bd79de176883e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853597"
---
# <a name="rangestep-function"></a><span data-ttu-id="fa795-102">RangeStep függvény</span><span class="sxs-lookup"><span data-stu-id="fa795-102">RangeStep function</span></span>

<span data-ttu-id="fa795-103">Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="fa795-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="fa795-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="fa795-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="fa795-105">Azt az egész számot adja vissza, amely megadja egy tartomány következő értékének kiszámítását.</span><span class="sxs-lookup"><span data-stu-id="fa795-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="fa795-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fa795-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="fa795-107">tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="fa795-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="fa795-108">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fa795-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fa795-109">A megadott tartomány megadott lépésének értéke.</span><span class="sxs-lookup"><span data-stu-id="fa795-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa795-110">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="fa795-110">Remarks</span></span>

<span data-ttu-id="fa795-111">A Range kifejezés első eleme a `start` , a második elem `start+step` , a harmadik elem `start+step+step` stb., amíg át nem `end` telik.</span><span class="sxs-lookup"><span data-stu-id="fa795-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>