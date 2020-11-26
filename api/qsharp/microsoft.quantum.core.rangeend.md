---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 90a9e31bf5c4a5e92a35998ddaec8c9e9de9888e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224037"
---
# <a name="rangeend-function"></a><span data-ttu-id="f7293-102">RangeEnd függvény</span><span class="sxs-lookup"><span data-stu-id="f7293-102">RangeEnd function</span></span>

<span data-ttu-id="f7293-103">Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="f7293-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="f7293-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f7293-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f7293-105">A megadott tartomány meghatározott záró értékét adja vissza, amely nem feltétlenül a sorrend utolsó eleme.</span><span class="sxs-lookup"><span data-stu-id="f7293-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="f7293-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f7293-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="f7293-107">tartomány: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="f7293-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="f7293-108">Kimenet: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f7293-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f7293-109">A megadott tartomány megadott záró értéke.</span><span class="sxs-lookup"><span data-stu-id="f7293-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="f7293-110">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="f7293-110">Remarks</span></span>

<span data-ttu-id="f7293-111">A Range kifejezés első eleme a `start` , a második elem `start+step` , a harmadik elem `start+step+step` stb., amíg át nem `end` telik.</span><span class="sxs-lookup"><span data-stu-id="f7293-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="f7293-112">Vegye figyelembe, hogy egy tartomány meghatározott záró értéke különbözhet a tartomány által meghatározott utolsó elemtől. például egy 0. tartományban.</span><span class="sxs-lookup"><span data-stu-id="f7293-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="f7293-113">2..</span><span class="sxs-lookup"><span data-stu-id="f7293-113">2 ..</span></span> <span data-ttu-id="f7293-114">5 az utolsó elem 4, a záró érték pedig 5.</span><span class="sxs-lookup"><span data-stu-id="f7293-114">5 the last element is 4 but the end value is 5.</span></span>