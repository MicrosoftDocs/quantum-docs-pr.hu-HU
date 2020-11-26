---
uid: Microsoft.Quantum.Simulation.IdentityGeneratorIndex
title: IdentityGeneratorIndex függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdentityGeneratorIndex
qsharp.summary: Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.
ms.openlocfilehash: 2dd3c705b0496df1719dc677e4defea5e435b839
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229290"
---
# <a name="identitygeneratorindex-function"></a><span data-ttu-id="69165-102">IdentityGeneratorIndex függvény</span><span class="sxs-lookup"><span data-stu-id="69165-102">IdentityGeneratorIndex function</span></span>

<span data-ttu-id="69165-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="69165-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="69165-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="69165-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="69165-105">Egy, a nulla Hamilton konzisztens generátor-indexet ad vissza, `H = 0` amely az Identity Evolution műveletnek felel meg.</span><span class="sxs-lookup"><span data-stu-id="69165-105">Returns a generator index consistent with the zero Hamiltonian, `H = 0`, which corresponds to the identity evolution operation.</span></span>

```qsharp
function IdentityGeneratorIndex (idxTerm : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a><span data-ttu-id="69165-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="69165-106">Input</span></span>

### <a name="idxterm--int"></a><span data-ttu-id="69165-107">idxTerm: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="69165-107">idxTerm : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="69165-108">A rendszer figyelmen kívül hagyja ezt a bemenetet, és a <xref:microsoft.quantum.simulation.generatorsystem> felhasználó által definiált típussal való konzisztencia meghatározására van beállítva.</span><span class="sxs-lookup"><span data-stu-id="69165-108">This input is ignored, and is defined for consistency with the <xref:microsoft.quantum.simulation.generatorsystem> user-defined type.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="69165-109">Kimenet: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="69165-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="69165-110">A Hamilton $H = $0.</span><span class="sxs-lookup"><span data-stu-id="69165-110">A generator index representing evolution under the Hamiltonian $H = 0$.</span></span>