---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 5b04e8c860a4bd6af7b10b4dbf803b1eb69ef5d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831117"
---
# <a name="rangestart-function"></a><span data-ttu-id="b87ef-102">RangeStart függvény</span><span class="sxs-lookup"><span data-stu-id="b87ef-102">RangeStart function</span></span>

<span data-ttu-id="b87ef-103">Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="b87ef-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="b87ef-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="b87ef-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="b87ef-105">A megadott tartomány megadott indítási értékét adja vissza.</span><span class="sxs-lookup"><span data-stu-id="b87ef-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="b87ef-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b87ef-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="b87ef-107">tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="b87ef-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="b87ef-108">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b87ef-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b87ef-109">A megadott tartomány megadott indítási értéke.</span><span class="sxs-lookup"><span data-stu-id="b87ef-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="b87ef-110">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b87ef-110">Remarks</span></span>

<span data-ttu-id="b87ef-111">A Range kifejezés első eleme a `start` , a második elem `start+step` , a harmadik elem `start+step+step` stb., amíg át nem `end` telik.</span><span class="sxs-lookup"><span data-stu-id="b87ef-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="b87ef-112">Vegye figyelembe, hogy a tartomány definiált indítási értéke megegyezik a sor első elemével, kivéve, ha a tartomány üres sorozatot ad meg (például 2..</span><span class="sxs-lookup"><span data-stu-id="b87ef-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="b87ef-113">1).</span><span class="sxs-lookup"><span data-stu-id="b87ef-113">1).</span></span>