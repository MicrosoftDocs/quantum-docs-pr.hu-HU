---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: e33d25899580a127171fb45a92d77cfdb5003a21
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201903"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="fd347-102">EqualityFactC függvény</span><span class="sxs-lookup"><span data-stu-id="fd347-102">EqualityFactC function</span></span>

<span data-ttu-id="fd347-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="fd347-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="fd347-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fd347-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fd347-105">Azt állítja, hogy egy összetett szám a várt értékkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="fd347-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="fd347-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="fd347-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="fd347-107">tényleges: [komplex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="fd347-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="fd347-108">Az ellenőrizendő érték.</span><span class="sxs-lookup"><span data-stu-id="fd347-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="fd347-109">várt: [komplex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="fd347-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="fd347-110">A várt érték.</span><span class="sxs-lookup"><span data-stu-id="fd347-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="fd347-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="fd347-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="fd347-112">Az érvényesítési művelet elindításakor használandó hibaüzenet karakterlánca.</span><span class="sxs-lookup"><span data-stu-id="fd347-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fd347-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fd347-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

