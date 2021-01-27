---
uid: Microsoft.Quantum.Synthesis.ApplyUnitary
title: ApplyUnitary művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyUnitary
qsharp.summary: >-
  Applies gate defined by 2^n x 2^n unitary matrix.

  Fails if matrix is not unitary, or has wrong size.
ms.openlocfilehash: 58215d3b05b8c6974e979d21a13869f27b436310
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859214"
---
# <a name="applyunitary-operation"></a><span data-ttu-id="f2605-102">ApplyUnitary művelet</span><span class="sxs-lookup"><span data-stu-id="f2605-102">ApplyUnitary operation</span></span>

<span data-ttu-id="f2605-103">Névtér: [Microsoft. Quantum. szintézis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="f2605-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="f2605-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f2605-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f2605-105">A 2 ^ n x 2 ^ n egységes mátrix által definiált kaput alkalmazza.</span><span class="sxs-lookup"><span data-stu-id="f2605-105">Applies gate defined by 2^n x 2^n unitary matrix.</span></span>

<span data-ttu-id="f2605-106">Sikertelen, ha a mátrix nem egységes, vagy nem megfelelő méretű.</span><span class="sxs-lookup"><span data-stu-id="f2605-106">Fails if matrix is not unitary, or has wrong size.</span></span>

```qsharp
operation ApplyUnitary (unitary : Microsoft.Quantum.Math.Complex[][], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="f2605-107">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f2605-107">Input</span></span>

### <a name="unitary--complex"></a><span data-ttu-id="f2605-108">egységes: [komplex](xref:Microsoft.Quantum.Math.Complex)[] []</span><span class="sxs-lookup"><span data-stu-id="f2605-108">unitary : [Complex](xref:Microsoft.Quantum.Math.Complex)[][]</span></span>

<span data-ttu-id="f2605-109">2 ^ n x 2 ^ n egységes mátrix, amely leírja a műveletet.</span><span class="sxs-lookup"><span data-stu-id="f2605-109">2^n x 2^n unitary matrix describing the operation.</span></span>
<span data-ttu-id="f2605-110">Ha a mátrix nem egységes, vagy nem megfelelő méretű, kivételt vet fel.</span><span class="sxs-lookup"><span data-stu-id="f2605-110">If matrix is not unitary or not of suitable size, throws an exception.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="f2605-111">qubits: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="f2605-111">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="f2605-112">Qubits, amelyre alkalmazni kell a műveletet – n hosszú regisztráció.</span><span class="sxs-lookup"><span data-stu-id="f2605-112">Qubits to which apply the operation - register of length n.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f2605-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f2605-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

