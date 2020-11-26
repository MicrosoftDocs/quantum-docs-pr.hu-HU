---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Ellentmondásos függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: f9ad9a7d67bda8e50c76f679f535ad55ba07698e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202141"
---
# <a name="contradiction-function"></a><span data-ttu-id="e967d-102">Ellentmondásos függvény</span><span class="sxs-lookup"><span data-stu-id="e967d-102">Contradiction function</span></span>

<span data-ttu-id="e967d-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e967d-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e967d-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="e967d-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="e967d-105">Kijelenti, hogy a klasszikus feltétel hamis.</span><span class="sxs-lookup"><span data-stu-id="e967d-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="e967d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e967d-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="e967d-107">tényleges: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="e967d-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e967d-108">A deklarált feltétel.</span><span class="sxs-lookup"><span data-stu-id="e967d-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="e967d-109">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="e967d-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="e967d-110">Az üzenet azon karakterlánca, melyet ki kell nyomtatni abban az esetben, ha a klasszikus feltétel igaz.</span><span class="sxs-lookup"><span data-stu-id="e967d-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e967d-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e967d-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="see-also"></a><span data-ttu-id="e967d-112">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="e967d-112">See Also</span></span>

- [<span data-ttu-id="e967d-113">Microsoft. Quantum. Diagnostics. Fact</span><span class="sxs-lookup"><span data-stu-id="e967d-113">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)