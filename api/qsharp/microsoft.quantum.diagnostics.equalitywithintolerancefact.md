---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: 6ada2632974fddd6dd0fd8e4e6ab0866e4f29524
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201716"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="e85e0-102">EqualityWithinToleranceFact függvény</span><span class="sxs-lookup"><span data-stu-id="e85e0-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="e85e0-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e85e0-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e85e0-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e85e0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e85e0-105">Azt a jogcímet jelöli, amely szerint egy klasszikus lebegőpontos érték a várt értékkel rendelkezik egy adott abszolút toleranciával.</span><span class="sxs-lookup"><span data-stu-id="e85e0-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="e85e0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e85e0-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="e85e0-107">tényleges: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e85e0-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e85e0-108">Az ellenőrizendő szám.</span><span class="sxs-lookup"><span data-stu-id="e85e0-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="e85e0-109">várt érték: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e85e0-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e85e0-110">A várt érték.</span><span class="sxs-lookup"><span data-stu-id="e85e0-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="e85e0-111">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e85e0-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e85e0-112">A tényleges és a várt érték közötti különbség abszolút tűréshatára.</span><span class="sxs-lookup"><span data-stu-id="e85e0-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e85e0-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e85e0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

