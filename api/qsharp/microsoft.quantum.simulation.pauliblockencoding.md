---
uid: Microsoft.Quantum.Simulation.PauliBlockEncoding
title: PauliBlockEncoding függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliBlockEncoding
qsharp.summary: >-
  Creates a block-encoding unitary for a Hamiltonian.

  The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.
ms.openlocfilehash: 2e37b40c60d19aa747114de988dddc19f0d7c50b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848006"
---
# <a name="pauliblockencoding-function"></a><span data-ttu-id="b9492-102">PauliBlockEncoding függvény</span><span class="sxs-lookup"><span data-stu-id="b9492-102">PauliBlockEncoding function</span></span>

<span data-ttu-id="b9492-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="b9492-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="b9492-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b9492-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b9492-105">Létrehoz egy blokk-Encoding egységes Hamilton.</span><span class="sxs-lookup"><span data-stu-id="b9492-105">Creates a block-encoding unitary for a Hamiltonian.</span></span>

<span data-ttu-id="b9492-106">A Hamilton $H = \ sum_ {j} \ alpha_j P_j $ kifejezést $P _j $ értékkel rendelkező, az összes valós hatékonyságú $ \ alpha_j $ nevű összeg írja le.</span><span class="sxs-lookup"><span data-stu-id="b9492-106">The Hamiltonian $H=\sum_{j}\alpha_j P_j$ is described by a sum of Pauli terms $P_j$, each with real coefficient $\alpha_j$.</span></span>

```qsharp
function PauliBlockEncoding (generatorSystem : Microsoft.Quantum.Simulation.GeneratorSystem) : (Double, Microsoft.Quantum.Simulation.BlockEncodingReflection)
```


## <a name="input"></a><span data-ttu-id="b9492-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="b9492-107">Input</span></span>

### <a name="generatorsystem--generatorsystem"></a><span data-ttu-id="b9492-108">generatorSystem: [generatorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="b9492-108">generatorSystem : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="b9492-109">A `GeneratorSystem` amely a $H $-t írja le a Pauli-kifejezések összegeként</span><span class="sxs-lookup"><span data-stu-id="b9492-109">A `GeneratorSystem` that describes $H$ as a sum of Pauli terms</span></span>



## <a name="output--doubleblockencodingreflection"></a><span data-ttu-id="b9492-110">Kimenet: ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span><span class="sxs-lookup"><span data-stu-id="b9492-110">Output : ([Double](xref:microsoft.quantum.lang-ref.double),[BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="b9492-111">Első paraméter</span><span class="sxs-lookup"><span data-stu-id="b9492-111">First parameter</span></span>

<span data-ttu-id="b9492-112">Az együtthatók egy normája: $ \alpha = \ sum_ {j} | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="b9492-112">The one-norm of coefficients $\alpha=\sum_{j}|\alpha_j|$.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="b9492-113">Második paraméter</span><span class="sxs-lookup"><span data-stu-id="b9492-113">Second parameter</span></span>

<span data-ttu-id="b9492-114">A `BlockEncodingReflection` Hamilton egységes $U $ $H $.</span><span class="sxs-lookup"><span data-stu-id="b9492-114">A `BlockEncodingReflection` unitary $U$ of the Hamiltonian $H$.</span></span> <span data-ttu-id="b9492-115">Mivel ez az egységes megfelel a $U ^ 2 = I $-nek, azt is tükrözi.</span><span class="sxs-lookup"><span data-stu-id="b9492-115">As this unitary satisfies $U^2 = I$, it is also a reflection.</span></span>

## <a name="remarks"></a><span data-ttu-id="b9492-116">Megjegyzések</span><span class="sxs-lookup"><span data-stu-id="b9492-116">Remarks</span></span>

<span data-ttu-id="b9492-117">Ezt a rendszer a $ \ sum_ {j} \sqrt{\ alpha_j/\alpha}\ket{j} $ állapotának előkészítésével és előkészítésével, valamint a szorzás által vezérelt egységes és a létrehozásával szerzi be <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator> .</span><span class="sxs-lookup"><span data-stu-id="b9492-117">This is obtained by preparing and unpreparing the state $\sum_{j}\sqrt{\alpha_j/\alpha}\ket{j}$, and constructing a multiply-controlled unitary <xref:microsoft.quantum.preparation.statepreparationpositivecoefficients> and <xref:microsoft.quantum.canon.multiplexoperationsfromgenerator>.</span></span>