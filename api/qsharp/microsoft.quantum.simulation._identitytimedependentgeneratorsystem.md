---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: _IdentityTimeDependentGeneratorSystem függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 7b93a6674bec974e61496696a3d8403225b16d80
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225601"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a><span data-ttu-id="35bf0-102">_IdentityTimeDependentGeneratorSystem függvény</span><span class="sxs-lookup"><span data-stu-id="35bf0-102">_IdentityTimeDependentGeneratorSystem function</span></span>

<span data-ttu-id="35bf0-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="35bf0-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="35bf0-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="35bf0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="35bf0-105">A Hamilton konzisztens Generátorrendszer visszaadása `H(s) = 0` , ahol a egy `s` Schedule paraméter.</span><span class="sxs-lookup"><span data-stu-id="35bf0-105">Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.</span></span>

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="35bf0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="35bf0-106">Input</span></span>

### <a name="schedule--double"></a><span data-ttu-id="35bf0-107">ütemterv: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="35bf0-107">schedule : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="35bf0-108">A rendszer figyelmen kívül hagyja ezt a bemenetet, és a <xref:microsoft.quantum.canon.timedependentgeneratorsystem> felhasználó által definiált típussal való konzisztencia meghatározására van beállítva.</span><span class="sxs-lookup"><span data-stu-id="35bf0-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.canon.timedependentgeneratorsystem> user-defined type.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="35bf0-109">Kimenet: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="35bf0-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="35bf0-110">A Hamilton-$H (ok) = $0-as számú, az összes $s $-hoz való evolúciót képviselő létrehozó rendszer.</span><span class="sxs-lookup"><span data-stu-id="35bf0-110">A generator system representing evolution under the Hamiltonian $H(s) = 0$ for all $s$.</span></span>