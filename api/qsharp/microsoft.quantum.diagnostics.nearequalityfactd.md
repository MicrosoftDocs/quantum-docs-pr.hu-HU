---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: d632a7a12c9ebbebfbc7939f2b8a24de8ae1ba2a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827895"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="7629a-102">NearEqualityFactD függvény</span><span class="sxs-lookup"><span data-stu-id="7629a-102">NearEqualityFactD function</span></span>

<span data-ttu-id="7629a-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="7629a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="7629a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7629a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7629a-105">Azt állítja, hogy egy klasszikus lebegőpontos érték a várt értékkel rendelkezik a 1e-10 kis tűréshatára alapján.</span><span class="sxs-lookup"><span data-stu-id="7629a-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="7629a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="7629a-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="7629a-107">tényleges: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7629a-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7629a-108">Az ellenőrizendő szám.</span><span class="sxs-lookup"><span data-stu-id="7629a-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="7629a-109">várt érték: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7629a-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7629a-110">A várt érték.</span><span class="sxs-lookup"><span data-stu-id="7629a-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7629a-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7629a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="7629a-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="7629a-112">Remarks</span></span>

<span data-ttu-id="7629a-113">Ez egyenértékű a <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> $10 ^ $ hardcoded-tűréssel {-10} .</span><span class="sxs-lookup"><span data-stu-id="7629a-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>