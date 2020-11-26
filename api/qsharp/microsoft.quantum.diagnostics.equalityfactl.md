---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 2aaabf39d6ce49952466a877685776490ef438ad
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201801"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="86a17-102">EqualityFactL függvény</span><span class="sxs-lookup"><span data-stu-id="86a17-102">EqualityFactL function</span></span>

<span data-ttu-id="86a17-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="86a17-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="86a17-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="86a17-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="86a17-105">Azt állítja be, hogy a klasszikus BigInt változó a várt értékkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="86a17-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="86a17-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="86a17-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="86a17-107">tényleges: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="86a17-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="86a17-108">Az ellenőrizendő szám.</span><span class="sxs-lookup"><span data-stu-id="86a17-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="86a17-109">várt: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="86a17-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="86a17-110">A várt érték.</span><span class="sxs-lookup"><span data-stu-id="86a17-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="86a17-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="86a17-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="86a17-112">Az érvényesítési művelet elindításakor használandó hibaüzenet karakterlánca.</span><span class="sxs-lookup"><span data-stu-id="86a17-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="86a17-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="86a17-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

