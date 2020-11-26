---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 39b55e17302f9d2e5049169e9c1a74e53a8b1115
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201852"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="368e0-102">EqualityFactCP függvény</span><span class="sxs-lookup"><span data-stu-id="368e0-102">EqualityFactCP function</span></span>

<span data-ttu-id="368e0-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="368e0-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="368e0-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="368e0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="368e0-105">Azt állítja, hogy egy összetett szám a várt értékkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="368e0-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="368e0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="368e0-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="368e0-107">tényleges: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="368e0-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="368e0-108">Az ellenőrizendő érték.</span><span class="sxs-lookup"><span data-stu-id="368e0-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="368e0-109">várt: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="368e0-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="368e0-110">A várt érték.</span><span class="sxs-lookup"><span data-stu-id="368e0-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="368e0-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="368e0-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="368e0-112">Az érvényesítési művelet elindításakor használandó hibaüzenet karakterlánca.</span><span class="sxs-lookup"><span data-stu-id="368e0-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="368e0-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="368e0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

