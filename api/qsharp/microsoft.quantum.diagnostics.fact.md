---
uid: Microsoft.Quantum.Diagnostics.Fact
title: Fact függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Fact
qsharp.summary: Declares that a classical condition is true.
ms.openlocfilehash: 8e86000f04c01040d420c2f682fc1b4ccf35cf39
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853309"
---
# <a name="fact-function"></a><span data-ttu-id="815ce-102">Fact függvény</span><span class="sxs-lookup"><span data-stu-id="815ce-102">Fact function</span></span>

<span data-ttu-id="815ce-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="815ce-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="815ce-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="815ce-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="815ce-105">Kijelenti, hogy a klasszikus feltétel igaz.</span><span class="sxs-lookup"><span data-stu-id="815ce-105">Declares that a classical condition is true.</span></span>

```qsharp
function Fact (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="815ce-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="815ce-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="815ce-107">tényleges: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="815ce-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="815ce-108">A deklarált feltétel.</span><span class="sxs-lookup"><span data-stu-id="815ce-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="815ce-109">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="815ce-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="815ce-110">Az üzenet azon karakterlánca, amelyet ki kell nyomtatni abban az esetben, ha a klasszikus feltétel hamis.</span><span class="sxs-lookup"><span data-stu-id="815ce-110">Failure message string to be printed in the case that the classical condition is false.</span></span>



## <a name="output--unit"></a><span data-ttu-id="815ce-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="815ce-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="815ce-112">Példa</span><span class="sxs-lookup"><span data-stu-id="815ce-112">Example</span></span>

<span data-ttu-id="815ce-113">A következő Q # kódrészlet sikertelen lesz:</span><span class="sxs-lookup"><span data-stu-id="815ce-113">The following Q# snippet will fail:</span></span>

```qsharp
Fact(false, "Expected true.");
```

## <a name="see-also"></a><span data-ttu-id="815ce-114">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="815ce-114">See Also</span></span>

- [<span data-ttu-id="815ce-115">Microsoft. Quantum. Diagnostics. ellentmondás</span><span class="sxs-lookup"><span data-stu-id="815ce-115">Microsoft.Quantum.Diagnostics.Contradiction</span></span>](xref:Microsoft.Quantum.Diagnostics.Contradiction)