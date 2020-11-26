---
uid: Microsoft.Quantum.Diagnostics.EqualityFactR
title: EqualityFactR függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactR
qsharp.summary: Asserts that a classical Result variable has the expected value.
ms.openlocfilehash: 166dff211d6db9da5d39c607af1924ffd6d276dd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201767"
---
# <a name="equalityfactr-function"></a><span data-ttu-id="16a12-102">EqualityFactR függvény</span><span class="sxs-lookup"><span data-stu-id="16a12-102">EqualityFactR function</span></span>

<span data-ttu-id="16a12-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="16a12-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="16a12-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="16a12-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="16a12-105">Azt állítja be, hogy egy klasszikus eredmény változó a várt értékkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="16a12-105">Asserts that a classical Result variable has the expected value.</span></span>

```qsharp
function EqualityFactR (actual : Result, expected : Result, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="16a12-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="16a12-106">Input</span></span>

### <a name="actual--__invalidresult__"></a><span data-ttu-id="16a12-107">tényleges: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="16a12-107">actual : __invalid<Result>__</span></span>

<span data-ttu-id="16a12-108">Az ellenőrizendő változó.</span><span class="sxs-lookup"><span data-stu-id="16a12-108">The variable to be checked.</span></span>


### <a name="expected--__invalidresult__"></a><span data-ttu-id="16a12-109">várt: __érvénytelen <Result>__</span><span class="sxs-lookup"><span data-stu-id="16a12-109">expected : __invalid<Result>__</span></span>

<span data-ttu-id="16a12-110">A várt érték.</span><span class="sxs-lookup"><span data-stu-id="16a12-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="16a12-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="16a12-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="16a12-112">Az érvényesítési művelet elindításakor használandó hibaüzenet karakterlánca.</span><span class="sxs-lookup"><span data-stu-id="16a12-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="16a12-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="16a12-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

