---
uid: Microsoft.Quantum.Diagnostics.NearEqualityFactCP
title: NearEqualityFactCP függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: NearEqualityFactCP
qsharp.summary: Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.
ms.openlocfilehash: 95364541adfa1dc57b1f147c3992c9fd9f5f6c68
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201563"
---
# <a name="nearequalityfactcp-function"></a><span data-ttu-id="6e26a-102">NearEqualityFactCP függvény</span><span class="sxs-lookup"><span data-stu-id="6e26a-102">NearEqualityFactCP function</span></span>

<span data-ttu-id="6e26a-103">Névtér: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="6e26a-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="6e26a-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6e26a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6e26a-105">Azt állítja, hogy a klasszikus komplex szám a várt értékkel rendelkezik a 1e-10 kis tűréshatára alapján.</span><span class="sxs-lookup"><span data-stu-id="6e26a-105">Asserts that a classical complex number has the expected value up to a small tolerance of 1e-10.</span></span>

```qsharp
function NearEqualityFactCP (actual : Microsoft.Quantum.Math.ComplexPolar, expected : Microsoft.Quantum.Math.ComplexPolar) : Unit
```


## <a name="input"></a><span data-ttu-id="6e26a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6e26a-106">Input</span></span>

### <a name="actual--complexpolar"></a><span data-ttu-id="6e26a-107">tényleges: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="6e26a-107">actual : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="6e26a-108">Az ellenőrizendő szám.</span><span class="sxs-lookup"><span data-stu-id="6e26a-108">The number to be checked.</span></span>


### <a name="expected--complexpolar"></a><span data-ttu-id="6e26a-109">várt: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="6e26a-109">expected : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="6e26a-110">A várt érték.</span><span class="sxs-lookup"><span data-stu-id="6e26a-110">The expected value.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6e26a-111">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6e26a-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

