---
uid: Microsoft.Quantum.Diagnostics.EqualityFactI
title: EqualityFactI függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactI
qsharp.summary: Asserts that a classical Int variable has the expected value.
ms.openlocfilehash: c41cb5548e8dfebb4d1c1a1c052306878c85e821
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853350"
---
# <a name="equalityfacti-function"></a><span data-ttu-id="eded8-102">EqualityFactI függvény</span><span class="sxs-lookup"><span data-stu-id="eded8-102">EqualityFactI function</span></span>

<span data-ttu-id="eded8-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="eded8-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="eded8-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="eded8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="eded8-105">Azt állítja be, hogy a klasszikus int változó a várt értékkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="eded8-105">Asserts that a classical Int variable has the expected value.</span></span>

```qsharp
function EqualityFactI (actual : Int, expected : Int, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="eded8-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="eded8-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="eded8-107">tényleges: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eded8-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eded8-108">Az ellenőrizendő szám.</span><span class="sxs-lookup"><span data-stu-id="eded8-108">The number to be checked.</span></span>


### <a name="expected--int"></a><span data-ttu-id="eded8-109">várt: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="eded8-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="eded8-110">A várt érték.</span><span class="sxs-lookup"><span data-stu-id="eded8-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="eded8-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="eded8-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="eded8-112">Az érvényesítési művelet elindításakor használandó hibaüzenet karakterlánca.</span><span class="sxs-lookup"><span data-stu-id="eded8-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eded8-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eded8-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

