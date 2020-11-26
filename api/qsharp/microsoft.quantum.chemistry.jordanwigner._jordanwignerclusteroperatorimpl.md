---
uid: Microsoft.Quantum.Chemistry.JordanWigner._JordanWignerClusterOperatorImpl
title: _JordanWignerClusterOperatorImpl művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _JordanWignerClusterOperatorImpl
qsharp.summary: >-
  Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.

  See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.
ms.openlocfilehash: 9a01742f25790e32d1787cc6cc266407de909c16
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96215741"
---
# <a name="_jordanwignerclusteroperatorimpl-operation"></a><span data-ttu-id="4496c-102">_JordanWignerClusterOperatorImpl művelet</span><span class="sxs-lookup"><span data-stu-id="4496c-102">_JordanWignerClusterOperatorImpl operation</span></span>

<span data-ttu-id="4496c-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="4496c-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="4496c-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4496c-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="4496c-105">A dinamikus generátort szimulálható kapuk készlete jelöli, a JordanWigner pedig kibővíthető.</span><span class="sxs-lookup"><span data-stu-id="4496c-105">Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.</span></span>

<span data-ttu-id="4496c-106">További részletekért lásd a [Dynamic Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) című témakört.</span><span class="sxs-lookup"><span data-stu-id="4496c-106">See [Dynamical Generator Modeling](../libraries/data-structures#dynamical-generator-modeling) for more details.</span></span>

```qsharp
operation _JordanWignerClusterOperatorImpl (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4496c-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4496c-107">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="4496c-108">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="4496c-108">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="4496c-109">Egy, az JordanWigner-ben egységes evolúcióként megjeleníteni kívánt generátor-index.</span><span class="sxs-lookup"><span data-stu-id="4496c-109">A generator index to be represented as unitary evolution in the JordanWigner.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="4496c-110">stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4496c-110">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4496c-111">A szimulációs algoritmusok aláírásának megfelelő dummy változó.</span><span class="sxs-lookup"><span data-stu-id="4496c-111">Dummy variable to match signature of simulation algorithms.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="4496c-112">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="4496c-112">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="4496c-113">A regisztráció az idő-Evolution operátorral végezhető el.</span><span class="sxs-lookup"><span data-stu-id="4496c-113">Register acted upon by time-evolution operator.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4496c-114">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4496c-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

