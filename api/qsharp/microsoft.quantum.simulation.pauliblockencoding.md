---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 1426c7cbc257f9263ff45a96738fe798c3679ba1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720220"
---
# <a name="pauliblockencoding-function"></a><span data-ttu-id="b8b7b-102">PauliBlockEncoding függvény</span><span class="sxs-lookup"><span data-stu-id="b8b7b-102">PauliBlockEncoding function</span></span>

<span data-ttu-id="b8b7b-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b8b7b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b8b7b-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b8b7b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b8b7b-105">Létrehoz egy blokk-Encoding egységes Hamilton.</span><span class="sxs-lookup"><span data-stu-id="b8b7b-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="b8b7b-106">A Hamilton $H = \ sum_ {j} \ alpha_j P_j $ kifejezést $P _j $ értékkel rendelkező, az összes valós hatékonyságú $ \ alpha_j $ nevű összeg írja le.</span><span class="sxs-lookup"><span data-stu-id="b8b7b-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="b8b7b-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b8b7b-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="b8b7b-108">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="b8b7b-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="b8b7b-109">A `GeneratorSystem` amely a $H $-t írja le a Pauli-kifejezések összegeként</span><span class="sxs-lookup"><span data-stu-id="b8b7b-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>



## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="b8b7b-110">Kimenet: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="b8b7b-110">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="b8b7b-111">Első paraméter</span><span class="sxs-lookup"><span data-stu-id="b8b7b-111">First parameter</span></span>

<span data-ttu-id="b8b7b-112">Az együtthatók egy normája: $ \alpha = \ sum_ {j} | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="b8b7b-112">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="b8b7b-113">Második paraméter</span><span class="sxs-lookup"><span data-stu-id="b8b7b-113">Second parameter</span></span>

<span data-ttu-id="b8b7b-114">A `BlockEncodingReflection` Hamilton egységes $U $ $H $.</span><span class="sxs-lookup"><span data-stu-id="b8b7b-114">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $H$.</span></span> <span data-ttu-id="b8b7b-115">Mivel ez az egységes megfelel a $U ^ 2 = I $-nek, azt is tükrözi.</span><span class="sxs-lookup"><span data-stu-id="b8b7b-115">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="b8b7b-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b8b7b-116">Remarks</span></span>

<span data-ttu-id="b8b7b-117">Ezt a rendszer a $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $ állapotának előkészítésével és előkészítésével, valamint a szorzás által vezérelt egységes és a létrehozásával szerzi be <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="b8b7b-117">This is obtained by preparing and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and constructing a multiply-controlled unitary <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>