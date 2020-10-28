---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713165"
---
# <a name="rangestart-function"></a><span data-ttu-id="de516-102">RangeStart függvény</span><span class="sxs-lookup"><span data-stu-id="de516-102">RangeStart function</span></span>

<span data-ttu-id="de516-103">Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="de516-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="de516-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="de516-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="de516-105">A megadott tartomány megadott indítási értékét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="de516-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="de516-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="de516-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="de516-107">tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="de516-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="de516-108">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="de516-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="de516-109">A megadott tartomány megadott indítási értéke.</span><span class="sxs-lookup"><span data-stu-id="de516-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="de516-110">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="de516-110">Remarks</span></span>

<span data-ttu-id="de516-111">A Range kifejezés első eleme a `start` , a második elem `start+step` , a harmadik elem `start+step+step` stb., amíg át nem `end` telik.</span><span class="sxs-lookup"><span data-stu-id="de516-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="de516-112">Vegye figyelembe, hogy a tartomány definiált indítási értéke megegyezik a sor első elemével, kivéve, ha a tartomány üres sorozatot ad meg (például 2..</span><span class="sxs-lookup"><span data-stu-id="de516-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="de516-113">1).</span><span class="sxs-lookup"><span data-stu-id="de516-113">1).</span></span>