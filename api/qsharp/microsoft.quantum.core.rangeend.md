---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 196fab0bd97a441a16976033dc0d660c54cdfd6a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831365"
---
# <a name="rangeend-function"></a><span data-ttu-id="8ab6e-102">RangeEnd függvény</span><span class="sxs-lookup"><span data-stu-id="8ab6e-102">RangeEnd function</span></span>

<span data-ttu-id="8ab6e-103">Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="8ab6e-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="8ab6e-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="8ab6e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="8ab6e-105">A megadott tartomány meghatározott záró értékét adja vissza, amely nem feltétlenül a sorrend utolsó eleme.</span><span class="sxs-lookup"><span data-stu-id="8ab6e-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="8ab6e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="8ab6e-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="8ab6e-107">tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="8ab6e-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="8ab6e-108">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8ab6e-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8ab6e-109">A megadott tartomány megadott záró értéke.</span><span class="sxs-lookup"><span data-stu-id="8ab6e-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="8ab6e-110">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="8ab6e-110">Remarks</span></span>

<span data-ttu-id="8ab6e-111">A Range kifejezés első eleme a `start` , a második elem `start+step` , a harmadik elem `start+step+step` stb., amíg át nem `end` telik.</span><span class="sxs-lookup"><span data-stu-id="8ab6e-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="8ab6e-112">Vegye figyelembe, hogy egy tartomány meghatározott záró értéke különbözhet a tartomány által meghatározott utolsó elemtől. például egy 0. tartományban.</span><span class="sxs-lookup"><span data-stu-id="8ab6e-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="8ab6e-113">2..</span><span class="sxs-lookup"><span data-stu-id="8ab6e-113">2 ..</span></span> <span data-ttu-id="8ab6e-114">5 az utolsó elem 4, a záró érték pedig 5.</span><span class="sxs-lookup"><span data-stu-id="8ab6e-114">5 the last element is 4 but the end value is 5.</span></span>