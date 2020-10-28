---
uid: Microsoft.Quantum.Preparation.BlochSphereCoordinates
title: BlochSphereCoordinates függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: BlochSphereCoordinates
qsharp.summary: >-
  Computes the Bloch sphere coordinates for a single-qubit state.

  Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.
ms.openlocfilehash: 6614b78c8e64c205cc94052cc64dd957814ab3d0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724075"
---
# <a name="blochspherecoordinates-function"></a><span data-ttu-id="6a793-102">BlochSphereCoordinates függvény</span><span class="sxs-lookup"><span data-stu-id="6a793-102">BlochSphereCoordinates function</span></span>

<span data-ttu-id="6a793-103">Névtér: [Microsoft. Quantum. előkészítés](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="6a793-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="6a793-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6a793-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6a793-105">Kiszámítja a Bloch gömb koordinátáit egy qubit állapothoz.</span><span class="sxs-lookup"><span data-stu-id="6a793-105">Computes the Bloch sphere coordinates for a single-qubit state.</span></span>

<span data-ttu-id="6a793-106">Az qubit-állapotot jelölő két összetett szám $a 0, a1 $, amely a Bloch szférán belüli számításokat mutatja be, így $a 0 \ket {0} + a1 \ket {1} = r e ^ {it} (e ^ {-i \phi/2}\cos{(\ THÉTA/2)} \ket {0} + e ^ {i \phi/2}\sin{(\ THÉTA/2)} \ket {1} ) $.</span><span class="sxs-lookup"><span data-stu-id="6a793-106">Given two complex numbers $a0, a1$ that represent the qubit state, computes coordinates on the Bloch sphere such that $a0 \ket{0} + a1 \ket{1} = r e^{it}(e^{-i \phi /2}\cos{(\theta/2)}\ket{0}+e^{i \phi /2}\sin{(\theta/2)}\ket{1})$.</span></span>

```qsharp
function BlochSphereCoordinates (a0 : Microsoft.Quantum.Math.ComplexPolar, a1 : Microsoft.Quantum.Math.ComplexPolar) : (Microsoft.Quantum.Math.ComplexPolar, Double, Double)
```


## <a name="input"></a><span data-ttu-id="6a793-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6a793-107">Input</span></span>

### <a name="a0--complexpolar"></a><span data-ttu-id="6a793-108">a0: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="6a793-108">a0 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="6a793-109">A \ket $ állapotú összetett együttható {0} .</span><span class="sxs-lookup"><span data-stu-id="6a793-109">Complex coefficient of state $\ket{0}$.</span></span>


### <a name="a1--complexpolar"></a><span data-ttu-id="6a793-110">a1: [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span><span class="sxs-lookup"><span data-stu-id="6a793-110">a1 : [ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar)</span></span>

<span data-ttu-id="6a793-111">A \ket $ állapotú összetett együttható {1} .</span><span class="sxs-lookup"><span data-stu-id="6a793-111">Complex coefficient of state $\ket{1}$.</span></span>



## <a name="output--complexpolardoubledouble"></a><span data-ttu-id="6a793-112">Kimenet: ([ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar),[dupla](xref:microsoft.quantum.lang-ref.double),[dupla](xref:microsoft.quantum.lang-ref.double))</span><span class="sxs-lookup"><span data-stu-id="6a793-112">Output : ([ComplexPolar](xref:Microsoft.Quantum.Math.ComplexPolar),[Double](xref:microsoft.quantum.lang-ref.double),[Double](xref:microsoft.quantum.lang-ref.double))</span></span>

<span data-ttu-id="6a793-113">Egy rekordot tartalmazó rekord `(ComplexPolar(r, t), phi, theta)` .</span><span class="sxs-lookup"><span data-stu-id="6a793-113">A tuple containing `(ComplexPolar(r, t), phi, theta)`.</span></span>