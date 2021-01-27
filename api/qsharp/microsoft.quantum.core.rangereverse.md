---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853658"
---
# <a name="rangereverse-function"></a><span data-ttu-id="46f64-102">RangeReverse függvény</span><span class="sxs-lookup"><span data-stu-id="46f64-102">RangeReverse function</span></span>

<span data-ttu-id="46f64-103">Névtér: [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="46f64-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="46f64-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="46f64-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="46f64-105">Egy új tartományt ad vissza, amely a bemeneti tartomány fordított értéke.</span><span class="sxs-lookup"><span data-stu-id="46f64-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="46f64-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="46f64-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="46f64-107">r: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="46f64-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="46f64-108">Bemeneti tartomány.</span><span class="sxs-lookup"><span data-stu-id="46f64-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="46f64-109">Kimenet: [tartomány](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="46f64-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="46f64-110">Egy új tartomány, amely a megadott tartomány fordítottja.</span><span class="sxs-lookup"><span data-stu-id="46f64-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="46f64-111">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="46f64-111">Remarks</span></span>

<span data-ttu-id="46f64-112">Vegye figyelembe, hogy a tartomány fordított értéke nem egyszerűen `end` .. `-step` . `start` , mert a tartomány tényleges utolsó eleme nem egyezhet meg `end` .</span><span class="sxs-lookup"><span data-stu-id="46f64-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>