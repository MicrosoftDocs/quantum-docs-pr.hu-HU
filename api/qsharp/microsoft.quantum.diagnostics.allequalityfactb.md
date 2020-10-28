---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactB
title: AllEqualityFactB függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactB
qsharp.summary: Asserts that two arrays of boolean values are equal.
ms.openlocfilehash: 100aacccbfd5b45ac9f859cd89424b0ed4007f72
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713080"
---
# <a name="allequalityfactb-function"></a><span data-ttu-id="1e080-102">AllEqualityFactB függvény</span><span class="sxs-lookup"><span data-stu-id="1e080-102">AllEqualityFactB function</span></span>

<span data-ttu-id="1e080-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="1e080-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="1e080-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="1e080-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="1e080-105">Azt állítja, hogy a logikai értékek két tömbje egyenlő.</span><span class="sxs-lookup"><span data-stu-id="1e080-105">Asserts that two arrays of boolean values are equal.</span></span>

```qsharp
function AllEqualityFactB (actual : Bool[], expected : Bool[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="1e080-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1e080-106">Input</span></span>

### <a name="actual--bool"></a><span data-ttu-id="1e080-107">tényleges: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="1e080-107">actual : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="1e080-108">Az a tömb, amelyet egy érdeklődési teszt esetén állít elő.</span><span class="sxs-lookup"><span data-stu-id="1e080-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--bool"></a><span data-ttu-id="1e080-109">várt: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="1e080-109">expected : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="1e080-110">Az a tömb, amely egy hasznos teszt esetén várható.</span><span class="sxs-lookup"><span data-stu-id="1e080-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="1e080-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="1e080-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="1e080-112">Egy nyomtatandó üzenet, ha a tömbök nem egyenlőek.</span><span class="sxs-lookup"><span data-stu-id="1e080-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1e080-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1e080-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

