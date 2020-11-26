---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactC
title: NearEqualityFactC függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactC
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: b08d5edcc1ead2cd125864a157efac76b72ba0d9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201614"
---
# <a name="nearequalityfactc-function"></a><span data-ttu-id="e1c60-102">NearEqualityFactC függvény</span><span class="sxs-lookup"><span data-stu-id="e1c60-102">NearEqualityFactC function</span></span>

<span data-ttu-id="e1c60-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="e1c60-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="e1c60-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e1c60-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e1c60-105">Azt állítja, hogy a klasszikus komplex szám a várt értékkel rendelkezik a 1e-10 kis tűréshatára alapján.</span><span class="sxs-lookup"><span data-stu-id="e1c60-105">Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactC (actual : Microsoft.Quantum.Math.Complex, expected : Microsoft.Quantum.Math.Complex) : Unit
```


## <a name="input"></a><span data-ttu-id="e1c60-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e1c60-106">Input</span></span>

### <a name="actual--complex"></a><span data-ttu-id="e1c60-107">tényleges: [komplex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="e1c60-107">actual : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="e1c60-108">Az ellenőrizendő szám.</span><span class="sxs-lookup"><span data-stu-id="e1c60-108">The number to be checked.</span></span>


### <a name="expected--complex"></a><span data-ttu-id="e1c60-109">várt: [komplex](xref:Microsoft.Quantum.Math.Complex)</span><span class="sxs-lookup"><span data-stu-id="e1c60-109">expected : [Complex](xref:Microsoft.Quantum.Math.Complex)</span></span>

<span data-ttu-id="e1c60-110">A várt érték.</span><span class="sxs-lookup"><span data-stu-id="e1c60-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e1c60-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e1c60-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

