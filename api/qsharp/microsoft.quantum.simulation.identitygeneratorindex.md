---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: d2af2dafaf75a68546cb3f16c04cf4c7ee50c6ff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724537"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="dad05-102">IdentityGeneratorIndex függvény</span><span class="sxs-lookup"><span data-stu-id="dad05-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="dad05-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="dad05-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="dad05-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="dad05-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="dad05-105">Egy, a nulla Hamilton konzisztens generátor-indexet ad vissza, `H = 0` amely az Identity Evolution műveletnek felel meg.</span><span class="sxs-lookup"><span data-stu-id="dad05-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="dad05-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="dad05-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="dad05-107">idxTerm: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="dad05-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="dad05-108">A rendszer figyelmen kívül hagyja ezt a bemenetet, és a <xref:microsoft.quantum.simulation.generatorsystem> felhasználó által definiált típussal való konzisztencia meghatározására van beállítva.</span><span class="sxs-lookup"><span data-stu-id="dad05-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="dad05-109">Kimenet: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="dad05-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="dad05-110">A Hamilton $H = $0.</span><span class="sxs-lookup"><span data-stu-id="dad05-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>