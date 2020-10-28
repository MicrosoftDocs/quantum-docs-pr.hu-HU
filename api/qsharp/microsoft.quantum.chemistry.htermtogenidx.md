---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: dd72355adb32f9a0d109ee36b24be2d445f3fa66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714831"
---
# <a name="htermtogenidx-function"></a><span data-ttu-id="e3cdf-102">HTermToGenIdx függvény</span><span class="sxs-lookup"><span data-stu-id="e3cdf-102">HTermToGenIdx function</span></span>

<span data-ttu-id="e3cdf-103">Névtér: [Microsoft. Quantum. kémia](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="e3cdf-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="e3cdf-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e3cdf-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e3cdf-105">Hamilton-kifejezést alakít át `HTerm` adatformátumba egy GeneratorIndex.</span><span class="sxs-lookup"><span data-stu-id="e3cdf-105">Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.</span></span>

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="e3cdf-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e3cdf-106">Input</span></span>

### <a name="term--hterm"></a><span data-ttu-id="e3cdf-107">kifejezés: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span><span class="sxs-lookup"><span data-stu-id="e3cdf-107">term : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)</span></span>

<span data-ttu-id="e3cdf-108">Bemeneti adatok `HTerm` formátumban.</span><span class="sxs-lookup"><span data-stu-id="e3cdf-108">Input data in `HTerm` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="e3cdf-109">Termináltípus: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e3cdf-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e3cdf-110">További információ a GeneratorIndex-hez.</span><span class="sxs-lookup"><span data-stu-id="e3cdf-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="e3cdf-111">Kimenet: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e3cdf-111">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e3cdf-112">A által reprezentált Hamilton kifejezést képviselő GeneratorIndex `term` , a által hozzáadott további információkkal együtt `termType` .</span><span class="sxs-lookup"><span data-stu-id="e3cdf-112">A GeneratorIndex representing a Hamiltonian term represented by `term`, together with additional information added by `termType`.</span></span>