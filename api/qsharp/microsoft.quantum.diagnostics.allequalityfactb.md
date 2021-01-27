---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 725291e8b5d12683ad580d5938dadd561831e88e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853557"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="2a58f-102">AllEqualityFactB függvény</span><span class="sxs-lookup"><span data-stu-id="2a58f-102">AllEqualityFactB function</span></span>

<span data-ttu-id="2a58f-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="2a58f-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="2a58f-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2a58f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2a58f-105">Azt állítja, hogy a logikai értékek két tömbje egyenlő.</span><span class="sxs-lookup"><span data-stu-id="2a58f-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="2a58f-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="2a58f-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="2a58f-107">tényleges: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="2a58f-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="2a58f-108">Az a tömb, amelyet egy érdeklődési teszt esetén állít elő.</span><span class="sxs-lookup"><span data-stu-id="2a58f-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="2a58f-109">várt: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="2a58f-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="2a58f-110">Az a tömb, amely egy hasznos teszt esetén várható.</span><span class="sxs-lookup"><span data-stu-id="2a58f-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="2a58f-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="2a58f-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="2a58f-112">Egy nyomtatandó üzenet, ha a tömbök nem egyenlőek.</span><span class="sxs-lookup"><span data-stu-id="2a58f-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2a58f-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2a58f-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

