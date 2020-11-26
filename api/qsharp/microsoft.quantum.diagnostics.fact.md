---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fact függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 74ec020d0437d885d7cbfc98a2c9c0c1867d5d39
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201682"
---
# <a name="fact-function"></a><span data-ttu-id="3e5dc-102">Fact függvény</span><span class="sxs-lookup"><span data-stu-id="3e5dc-102">Fact function</span></span>

<span data-ttu-id="3e5dc-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="3e5dc-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="3e5dc-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3e5dc-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3e5dc-105">Kijelenti, hogy a klasszikus feltétel igaz.</span><span class="sxs-lookup"><span data-stu-id="3e5dc-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="3e5dc-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3e5dc-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="3e5dc-107">tényleges: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3e5dc-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3e5dc-108">A deklarált feltétel.</span><span class="sxs-lookup"><span data-stu-id="3e5dc-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="3e5dc-109">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="3e5dc-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="3e5dc-110">Az üzenet azon karakterlánca, amelyet ki kell nyomtatni abban az esetben, ha a klasszikus feltétel hamis.</span><span class="sxs-lookup"><span data-stu-id="3e5dc-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3e5dc-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3e5dc-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="3e5dc-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="3e5dc-112">See Also</span></span>

- [<span data-ttu-id="3e5dc-113">Microsoft. Quantum. Diagnostics. ellentmondás</span><span class="sxs-lookup"><span data-stu-id="3e5dc-113">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)