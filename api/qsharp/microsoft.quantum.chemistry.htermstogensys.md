---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 936e1bcc58b2f1af3bdb606884128c38d2f58867
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204113"
---
# <a name="htermstogensys-function"></a><span data-ttu-id="0a51d-102">HTermsToGenSys függvény</span><span class="sxs-lookup"><span data-stu-id="0a51d-102">HTermsToGenSys function</span></span>

<span data-ttu-id="0a51d-103">Névtér: [Microsoft. Quantum. kémia](xref:Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="0a51d-103">Namespace: [Microsoft.Quantum.Chemistry](xref:Microsoft.Quantum.Chemistry)</span></span>

<span data-ttu-id="0a51d-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="0a51d-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="0a51d-105">Adatformátumba konvertál egy Hamilton `HTerm[]` egy GeneratorSystem.</span><span class="sxs-lookup"><span data-stu-id="0a51d-105">Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.</span></span>

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="0a51d-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0a51d-106">Input</span></span>

### <a name="data--hterm"></a><span data-ttu-id="0a51d-107">adatkezelés: [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span><span class="sxs-lookup"><span data-stu-id="0a51d-107">data : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]</span></span>

<span data-ttu-id="0a51d-108">Bemeneti adatok `HTerm[]` formátumban.</span><span class="sxs-lookup"><span data-stu-id="0a51d-108">Input data in `HTerm[]` format.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="0a51d-109">Termináltípus: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="0a51d-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="0a51d-110">További információ a GeneratorIndex-hez.</span><span class="sxs-lookup"><span data-stu-id="0a51d-110">Additional information added to GeneratorIndex.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="0a51d-111">Kimenet: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="0a51d-111">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="0a51d-112">A bemenet által reprezentált Hamilton jelképező GeneratorSystem `data` .</span><span class="sxs-lookup"><span data-stu-id="0a51d-112">A GeneratorSystem representing a Hamiltonian represented by the input `data`.</span></span>