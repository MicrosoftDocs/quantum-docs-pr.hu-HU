---
uid: Microsoft.Quantum.Diagnostics.EqualityFactL
title: EqualityFactL függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityFactL
qsharp.summary: Asserts that a classical BigInt variable has the expected value.
ms.openlocfilehash: 5e590af581be4e41df9d2081260409c454e3be4b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712758"
---
# <a name="equalityfactl-function"></a><span data-ttu-id="b6545-102">EqualityFactL függvény</span><span class="sxs-lookup"><span data-stu-id="b6545-102">EqualityFactL function</span></span>

<span data-ttu-id="b6545-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="b6545-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="b6545-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b6545-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b6545-105">Azt állítja be, hogy a klasszikus BigInt változó a várt értékkel rendelkezik.</span><span class="sxs-lookup"><span data-stu-id="b6545-105">Asserts that a classical BigInt variable has the expected value.</span></span>

```qsharp
function EqualityFactL (actual : BigInt, expected : BigInt, message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="b6545-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b6545-106">Input</span></span>

### <a name="actual--bigint"></a><span data-ttu-id="b6545-107">tényleges: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b6545-107">actual : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b6545-108">Az ellenőrizendő szám.</span><span class="sxs-lookup"><span data-stu-id="b6545-108">The number to be checked.</span></span>


### <a name="expected--bigint"></a><span data-ttu-id="b6545-109">várt: [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b6545-109">expected : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b6545-110">A várt érték.</span><span class="sxs-lookup"><span data-stu-id="b6545-110">The expected value.</span></span>


### <a name="message--string"></a><span data-ttu-id="b6545-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="b6545-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="b6545-112">Az érvényesítési művelet elindításakor használandó hibaüzenet karakterlánca.</span><span class="sxs-lookup"><span data-stu-id="b6545-112">Failure message string to be used when the assertion is triggered.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b6545-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b6545-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

