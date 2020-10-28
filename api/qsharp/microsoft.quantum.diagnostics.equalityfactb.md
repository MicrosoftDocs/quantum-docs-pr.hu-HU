---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: d3163281772bda392fbdd61ad58543e22022a600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712773"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="9ac99-102">EqualityFactB függvény</span><span class="sxs-lookup"><span data-stu-id="9ac99-102">EqualityFactB function</span></span>

<span data-ttu-id="9ac99-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9ac99-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9ac99-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9ac99-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9ac99-105">Azt állítja be, hogy a klasszikus bool változó a várt értékkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="9ac99-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="9ac99-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9ac99-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="9ac99-107">tényleges: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9ac99-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9ac99-108">Az ellenőrizendő változó.</span><span class="sxs-lookup"><span data-stu-id="9ac99-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="9ac99-109">várt: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9ac99-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9ac99-110">A várt érték.</span><span class="sxs-lookup"><span data-stu-id="9ac99-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="9ac99-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="9ac99-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="9ac99-112">Az érvényesítési művelet elindításakor használandó hibaüzenet karakterlánca.</span><span class="sxs-lookup"><span data-stu-id="9ac99-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9ac99-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9ac99-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

