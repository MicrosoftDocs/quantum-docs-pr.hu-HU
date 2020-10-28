---
uid: Microsoft.Quantum.Diagnostics.EqualityFactC
title: EqualityFactC függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactC
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 4c7256f9a8c84b4e105b1cbff6b18d6dd99cc441
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712786"
---
# <a name="equalityfactc-function"></a><span data-ttu-id="95a47-102">EqualityFactC függvény</span><span class="sxs-lookup"><span data-stu-id="95a47-102">EqualityFactC function</span></span>

<span data-ttu-id="95a47-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="95a47-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="95a47-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="95a47-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="95a47-105">Azt állítja, hogy egy összetett szám a várt értékkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="95a47-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="95a47-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="95a47-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="95a47-107">tényleges: [komplex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="95a47-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="95a47-108">Az ellenőrizendő érték.</span><span class="sxs-lookup"><span data-stu-id="95a47-108">The value to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="95a47-109">várt: [komplex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="95a47-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="95a47-110">A várt érték.</span><span class="sxs-lookup"><span data-stu-id="95a47-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="95a47-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="95a47-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="95a47-112">Az érvényesítési művelet elindításakor használandó hibaüzenet karakterlánca.</span><span class="sxs-lookup"><span data-stu-id="95a47-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="95a47-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="95a47-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

