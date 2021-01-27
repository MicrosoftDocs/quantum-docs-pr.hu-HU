---
uid: Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact
title: EqualityWithinToleranceFact függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: EqualityWithinToleranceFact
qsharp.summary: Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.
ms.openlocfilehash: ab7e43d951bf741926b15f27f94d176e88609d4a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98828752"
---
# <a name="equalitywithintolerancefact-function"></a><span data-ttu-id="77b29-102">EqualityWithinToleranceFact függvény</span><span class="sxs-lookup"><span data-stu-id="77b29-102">EqualityWithinToleranceFact function</span></span>

<span data-ttu-id="77b29-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="77b29-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="77b29-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="77b29-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="77b29-105">Azt a jogcímet jelöli, amely szerint egy klasszikus lebegőpontos érték a várt értékkel rendelkezik egy adott abszolút toleranciával.</span><span class="sxs-lookup"><span data-stu-id="77b29-105">Represents the claim that a classical floating point value has the expected value up to a given absolute tolerance.</span></span>

```qsharp
function EqualityWithinToleranceFact (actual : Double, expected : Double, tolerance : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="77b29-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="77b29-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="77b29-107">tényleges: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="77b29-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="77b29-108">Az ellenőrizendő szám.</span><span class="sxs-lookup"><span data-stu-id="77b29-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="77b29-109">várt érték: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="77b29-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="77b29-110">A várt érték.</span><span class="sxs-lookup"><span data-stu-id="77b29-110">The expected value.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="77b29-111">tolerancia: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="77b29-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="77b29-112">A tényleges és a várt érték közötti különbség abszolút tűréshatára.</span><span class="sxs-lookup"><span data-stu-id="77b29-112">Absolute tolerance on the difference between actual and expected.</span></span>



## <a name="output--unit"></a><span data-ttu-id="77b29-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="77b29-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

