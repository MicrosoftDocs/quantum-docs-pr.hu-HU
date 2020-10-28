---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerZTerm_
title: _ApplyJordanWignerZTerm_ művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerZTerm_
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: f42c2ba7570f32d3f26ff82dd4a0ee6f9677fa30
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714732"
---
# <a name="_applyjordanwignerzterm_-operation"></a><span data-ttu-id="37625-102">_ApplyJordanWignerZTerm_ művelet</span><span class="sxs-lookup"><span data-stu-id="37625-102">_ApplyJordanWignerZTerm_ operation</span></span>

<span data-ttu-id="37625-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="37625-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="37625-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="37625-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="37625-105">Alkalmazza az idő-evolúciót az a által leírt Z kifejezéssel `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="37625-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerZTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a><span data-ttu-id="37625-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="37625-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="37625-107">kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="37625-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="37625-108">`GeneratorIndex` egy Z kifejezést jelképez.</span><span class="sxs-lookup"><span data-stu-id="37625-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="37625-109">stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="37625-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="37625-110">Az idő időbeli alakulása.</span><span class="sxs-lookup"><span data-stu-id="37625-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="37625-111">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="37625-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="37625-112">A Hamilton qubits.</span><span class="sxs-lookup"><span data-stu-id="37625-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="37625-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="37625-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

