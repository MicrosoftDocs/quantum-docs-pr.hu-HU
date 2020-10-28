---
uid: Microsoft.Quantum.Diagnostics.EqualityFactCP
title: EqualityFactCP függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactCP
qsharp.summary: Asserts that a complex number has the expected value.
ms.openlocfilehash: 1ea790debb5a9123fb8bee3a5f8a1fde0a050b37
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712772"
---
# <a name="equalityfactcp-function"></a><span data-ttu-id="75ded-102">EqualityFactCP függvény</span><span class="sxs-lookup"><span data-stu-id="75ded-102">EqualityFactCP function</span></span>

<span data-ttu-id="75ded-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="75ded-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="75ded-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="75ded-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="75ded-105">Azt állítja, hogy egy összetett szám a várt értékkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="75ded-105">Asserts that a complex number has the expected value.</span></span>

```qsharp
function EqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="75ded-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="75ded-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="75ded-107">tényleges: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="75ded-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="75ded-108">Az ellenőrizendő érték.</span><span class="sxs-lookup"><span data-stu-id="75ded-108">The value to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="75ded-109">várt: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="75ded-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="75ded-110">A várt érték.</span><span class="sxs-lookup"><span data-stu-id="75ded-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="75ded-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="75ded-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="75ded-112">Az érvényesítési művelet elindításakor használandó hibaüzenet karakterlánca.</span><span class="sxs-lookup"><span data-stu-id="75ded-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="75ded-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="75ded-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

