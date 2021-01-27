---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 3d5963b8751a22d7116d6c1cf094d89e1d6b556f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851766"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="cda2c-102">HTermsToGenSys függvény</span><span class="sxs-lookup"><span data-stu-id="cda2c-102">HTermsToGenSys function</span></span>

<span data-ttu-id="cda2c-103">Névtér: [Microsoft. Quantum. kémia](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="cda2c-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="cda2c-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="cda2c-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="cda2c-105">Adatformátumba konvertál egy Hamilton `HTerm[]` egy GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="cda2c-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="cda2c-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="cda2c-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="cda2c-107">adatkezelés: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="cda2c-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="cda2c-108">Bemeneti adatok `HTerm[]` formátumban.</span><span class="sxs-lookup"><span data-stu-id="cda2c-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="cda2c-109">Termináltípus: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="cda2c-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="cda2c-110">További információ a GeneratorIndex-hez.</span><span class="sxs-lookup"><span data-stu-id="cda2c-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="cda2c-111">Kimenet: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="cda2c-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="cda2c-112">A bemenet által reprezentált Hamilton jelképező GeneratorSystem `data` .</span><span class="sxs-lookup"><span data-stu-id="cda2c-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>