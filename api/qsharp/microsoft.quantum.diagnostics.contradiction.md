---
uid: Microsoft.Quantum.Diagnostics.Contradiction
title: Ellentmondásos függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: Contradiction
qsharp.summary: Declares that a classical condition is false.
ms.openlocfilehash: 7d62c9341b768dfdfbfbf8e73e64748f04317595
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829365"
---
# <a name="contradiction-function"></a><span data-ttu-id="6eece-102">Ellentmondásos függvény</span><span class="sxs-lookup"><span data-stu-id="6eece-102">Contradiction function</span></span>

<span data-ttu-id="6eece-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6eece-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6eece-104">Csomag: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6eece-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6eece-105">Kijelenti, hogy a klasszikus feltétel hamis.</span><span class="sxs-lookup"><span data-stu-id="6eece-105">Declares that a classical condition is false.</span></span>

```qsharp
function Contradiction (actual : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="6eece-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6eece-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="6eece-107">tényleges: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6eece-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6eece-108">A deklarált feltétel.</span><span class="sxs-lookup"><span data-stu-id="6eece-108">The condition to be declared.</span></span>


### <a name="message--string"></a><span data-ttu-id="6eece-109">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="6eece-109">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="6eece-110">Az üzenet azon karakterlánca, melyet ki kell nyomtatni abban az esetben, ha a klasszikus feltétel igaz.</span><span class="sxs-lookup"><span data-stu-id="6eece-110">Failure message string to be printed in the case that the classical condition is true.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6eece-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6eece-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="example"></a><span data-ttu-id="6eece-112">Példa</span><span class="sxs-lookup"><span data-stu-id="6eece-112">Example</span></span>

<span data-ttu-id="6eece-113">A következő Q # kód a "Hello, World" kifejezést fogja kinyomtatni:</span><span class="sxs-lookup"><span data-stu-id="6eece-113">The following Q# code will print "Hello, world":</span></span>

```qsharp
Contradiction(2 == 3, "2 is not equal to 3.");
Message("Hello, world.");
```

## <a name="see-also"></a><span data-ttu-id="6eece-114">Lásd még:</span><span class="sxs-lookup"><span data-stu-id="6eece-114">See Also</span></span>

- [<span data-ttu-id="6eece-115">Microsoft. Quantum. Diagnostics. Fact</span><span class="sxs-lookup"><span data-stu-id="6eece-115">Microsoft.Quantum.Diagnostics.Fact</span></span>](xref:Microsoft.Quantum.Diagnostics.Fact)