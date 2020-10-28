---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Ellentmondásos függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: a5f3f26c5ada2eea9206699a2cc77575a9b5eebd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712870"
---
# <a name="contradiction-function"></a><span data-ttu-id="e3223-102">Ellentmondásos függvény</span><span class="sxs-lookup"><span data-stu-id="e3223-102">Contradiction function</span></span>

<span data-ttu-id="e3223-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e3223-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e3223-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e3223-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e3223-105">Kijelenti, hogy a klasszikus feltétel hamis.</span><span class="sxs-lookup"><span data-stu-id="e3223-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="e3223-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e3223-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="e3223-107">tényleges: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e3223-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e3223-108">A deklarált feltétel.</span><span class="sxs-lookup"><span data-stu-id="e3223-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="e3223-109">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e3223-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e3223-110">Az üzenet azon karakterlánca, melyet ki kell nyomtatni abban az esetben, ha a klasszikus feltétel igaz.</span><span class="sxs-lookup"><span data-stu-id="e3223-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e3223-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e3223-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e3223-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e3223-112">See Also</span></span>

- [<span data-ttu-id="e3223-113">Microsoft. Quantum. Diagnostics. Fact</span><span class="sxs-lookup"><span data-stu-id="e3223-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)