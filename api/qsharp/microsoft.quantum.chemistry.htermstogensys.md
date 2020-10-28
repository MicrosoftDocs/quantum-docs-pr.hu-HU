---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: b78ff393fa1e51c38028ef56bb3c61b8f1d5e478
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714844"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="3c23a-102">HTermsToGenSys függvény</span><span class="sxs-lookup"><span data-stu-id="3c23a-102">HTermsToGenSys function</span></span>

<span data-ttu-id="3c23a-103">Névtér: [Microsoft. Quantum. kémia](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="3c23a-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="3c23a-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3c23a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3c23a-105">Adatformátumba konvertál egy Hamilton `HTerm[]` egy GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="3c23a-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="3c23a-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="3c23a-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="3c23a-107">adatkezelés: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="3c23a-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="3c23a-108">Bemeneti adatok `HTerm[]` formátumban.</span><span class="sxs-lookup"><span data-stu-id="3c23a-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="3c23a-109">Termináltípus: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="3c23a-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="3c23a-110">További információ a GeneratorIndex-hez.</span><span class="sxs-lookup"><span data-stu-id="3c23a-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="3c23a-111">Kimenet: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="3c23a-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="3c23a-112">A bemenet által reprezentált Hamilton jelképező GeneratorSystem `data` .</span><span class="sxs-lookup"><span data-stu-id="3c23a-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>