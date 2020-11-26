---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactD
title: NearEqualityFactD függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactD
qsharp.summary: Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 5acfe5043342fd88276910a9fd0347f7d2f6960f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201512"
---
# <a name="nearequalityfactd-function"></a><span data-ttu-id="331ff-102">NearEqualityFactD függvény</span><span class="sxs-lookup"><span data-stu-id="331ff-102">NearEqualityFactD function</span></span>

<span data-ttu-id="331ff-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="331ff-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="331ff-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="331ff-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="331ff-105">Azt állítja, hogy egy klasszikus lebegőpontos érték a várt értékkel rendelkezik a 1e-10 kis tűréshatára alapján.</span><span class="sxs-lookup"><span data-stu-id="331ff-105">Asserts that a classical floating point value has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactD (actual : Double, expected : Double) : Unit
```


## <a name="input"></a><span data-ttu-id="331ff-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="331ff-106">Input</span></span>

### <a name="actual--double"></a><span data-ttu-id="331ff-107">tényleges: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="331ff-107">actual : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="331ff-108">Az ellenőrizendő szám.</span><span class="sxs-lookup"><span data-stu-id="331ff-108">The number to be checked.</span></span>


### <a name="expected--double"></a><span data-ttu-id="331ff-109">várt érték: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="331ff-109">expected : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="331ff-110">A várt érték.</span><span class="sxs-lookup"><span data-stu-id="331ff-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="331ff-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="331ff-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="331ff-112">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="331ff-112">Remarks</span></span>

<span data-ttu-id="331ff-113">Ez egyenértékű a <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> $10 ^ $ hardcoded-tűréssel {-10} .</span><span class="sxs-lookup"><span data-stu-id="331ff-113">This is equivalent to <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact> with hardcoded tolerance of $10^{-10}$.</span></span>