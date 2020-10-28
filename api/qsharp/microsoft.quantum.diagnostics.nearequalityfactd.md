---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5b55f515b27667071218a3f604ef703a6a15206d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712647"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="cab3a-102">NearEqualityFactD függvény</span><span class="sxs-lookup"><span data-stu-id="cab3a-102">NearEqualityFactD function</span></span>

<span data-ttu-id="cab3a-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="cab3a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="cab3a-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cab3a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cab3a-105">Azt állítja, hogy egy klasszikus lebegőpontos érték a várt értékkel rendelkezik a 1e-10 kis tűréshatára alapján.</span><span class="sxs-lookup"><span data-stu-id="cab3a-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="cab3a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="cab3a-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="cab3a-107">tényleges: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cab3a-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cab3a-108">Az ellenőrizendő szám.</span><span class="sxs-lookup"><span data-stu-id="cab3a-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="cab3a-109">várt érték: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cab3a-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cab3a-110">A várt érték.</span><span class="sxs-lookup"><span data-stu-id="cab3a-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cab3a-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cab3a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="cab3a-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="cab3a-112">Remarks</span></span>

<span data-ttu-id="cab3a-113">Ez egyenértékű a <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> $10 ^ $ hardcoded-tűréssel {-10} .</span><span class="sxs-lookup"><span data-stu-id="cab3a-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>