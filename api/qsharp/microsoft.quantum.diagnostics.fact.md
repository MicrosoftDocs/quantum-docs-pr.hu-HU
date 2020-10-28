---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fact függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 6a08703f68f9f38f2224fe4c6a4d255b00756908
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712688"
---
# <a name="fact-function"></a><span data-ttu-id="69bbd-102">Fact függvény</span><span class="sxs-lookup"><span data-stu-id="69bbd-102">Fact function</span></span>

<span data-ttu-id="69bbd-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="69bbd-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="69bbd-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="69bbd-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="69bbd-105">Kijelenti, hogy a klasszikus feltétel igaz.</span><span class="sxs-lookup"><span data-stu-id="69bbd-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="69bbd-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="69bbd-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="69bbd-107">tényleges: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="69bbd-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="69bbd-108">A deklarált feltétel.</span><span class="sxs-lookup"><span data-stu-id="69bbd-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="69bbd-109">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="69bbd-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="69bbd-110">Az üzenet azon karakterlánca, amelyet ki kell nyomtatni abban az esetben, ha a klasszikus feltétel hamis.</span><span class="sxs-lookup"><span data-stu-id="69bbd-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="69bbd-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="69bbd-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="69bbd-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="69bbd-112">See Also</span></span>

- [<span data-ttu-id="69bbd-113">Microsoft. Quantum. Diagnostics. ellentmondás</span><span class="sxs-lookup"><span data-stu-id="69bbd-113">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)