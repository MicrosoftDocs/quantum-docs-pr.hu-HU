---
uid: Microsoft.Quantum.Diagnostics.EqualityFactB
title: EqualityFactB függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactB
qsharp.summary: Asserts that a classical Bool variable has the expected value.
ms.openlocfilehash: a87d6690e701eb1530be3134d24884a8c19357e9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201920"
---
# <a name="equalityfactb-function"></a><span data-ttu-id="df4e1-102">EqualityFactB függvény</span><span class="sxs-lookup"><span data-stu-id="df4e1-102">EqualityFactB function</span></span>

<span data-ttu-id="df4e1-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="df4e1-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="df4e1-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="df4e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="df4e1-105">Azt állítja be, hogy a klasszikus bool változó a várt értékkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="df4e1-105">Asserts that a classical Bool variable has the expected value.</span></span>

```qsharp
function EqualityFactB (actual : Bool, expected : Bool, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="df4e1-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="df4e1-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="df4e1-107">tényleges: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="df4e1-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="df4e1-108">Az ellenőrizendő változó.</span><span class="sxs-lookup"><span data-stu-id="df4e1-108">The variable to be checked.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="df4e1-109">várt: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="df4e1-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="df4e1-110">A várt érték.</span><span class="sxs-lookup"><span data-stu-id="df4e1-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="df4e1-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="df4e1-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="df4e1-112">Az érvényesítési művelet elindításakor használandó hibaüzenet karakterlánca.</span><span class="sxs-lookup"><span data-stu-id="df4e1-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="df4e1-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="df4e1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

