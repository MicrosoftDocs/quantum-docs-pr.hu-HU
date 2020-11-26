---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: 92b57f49407d558e5f8d0365c168b7890f1f4981
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223884"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="9b79a-102">AllEqualityFactI függvény</span><span class="sxs-lookup"><span data-stu-id="9b79a-102">AllEqualityFactI function</span></span>

<span data-ttu-id="9b79a-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="9b79a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="9b79a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b79a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b79a-105">Azt állítja, hogy az egész értékek két tömbje egyenlő.</span><span class="sxs-lookup"><span data-stu-id="9b79a-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="9b79a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="9b79a-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="9b79a-107">tényleges: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9b79a-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9b79a-108">Az a tömb, amelyet egy érdeklődési teszt esetén állít elő.</span><span class="sxs-lookup"><span data-stu-id="9b79a-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="9b79a-109">várt: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="9b79a-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="9b79a-110">Az a tömb, amely egy hasznos teszt esetén várható.</span><span class="sxs-lookup"><span data-stu-id="9b79a-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="9b79a-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="9b79a-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="9b79a-112">Egy nyomtatandó üzenet, ha a tömbök nem egyenlőek.</span><span class="sxs-lookup"><span data-stu-id="9b79a-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9b79a-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b79a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

