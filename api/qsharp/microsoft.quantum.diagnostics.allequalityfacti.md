---
uid: Microsoft.Quantum.Diagnostics.AllEqualityFactI
title: AllEqualityFactI függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AllEqualityFactI
qsharp.summary: Asserts that two arrays of integer values are equal.
ms.openlocfilehash: a7043b9c670f79e270180c583fef56b70c1a3bcb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830891"
---
# <a name="allequalityfacti-function"></a><span data-ttu-id="bfb42-102">AllEqualityFactI függvény</span><span class="sxs-lookup"><span data-stu-id="bfb42-102">AllEqualityFactI function</span></span>

<span data-ttu-id="bfb42-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="bfb42-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="bfb42-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bfb42-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bfb42-105">Azt állítja, hogy az egész értékek két tömbje egyenlő.</span><span class="sxs-lookup"><span data-stu-id="bfb42-105">Asserts that two arrays of integer values are equal.</span></span>

```qsharp
function AllEqualityFactI (actual : Int[], expected : Int[], message : String) : Unit
```


## <a name="input"></a><span data-ttu-id="bfb42-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="bfb42-106">Input</span></span>

### <a name="actual--int"></a><span data-ttu-id="bfb42-107">tényleges: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="bfb42-107">actual : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="bfb42-108">Az a tömb, amelyet egy érdeklődési teszt esetén állít elő.</span><span class="sxs-lookup"><span data-stu-id="bfb42-108">The array that is produced by a test case of interest.</span></span>


### <a name="expected--int"></a><span data-ttu-id="bfb42-109">várt: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="bfb42-109">expected : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="bfb42-110">Az a tömb, amely egy hasznos teszt esetén várható.</span><span class="sxs-lookup"><span data-stu-id="bfb42-110">The array that is expected from a test case of interest.</span></span>


### <a name="message--string"></a><span data-ttu-id="bfb42-111">üzenet: [karakterlánc](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="bfb42-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="bfb42-112">Egy nyomtatandó üzenet, ha a tömbök nem egyenlőek.</span><span class="sxs-lookup"><span data-stu-id="bfb42-112">A message to be printed if the arrays are not equal.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bfb42-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bfb42-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

