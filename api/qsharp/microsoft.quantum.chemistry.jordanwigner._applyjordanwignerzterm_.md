---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerZTerm_
title: _ApplyJordanWignerZTerm_ művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerZTerm_
qsharp.summary: Applies time-evolution by a Z term described by a `GeneratorIndex`.
ms.openlocfilehash: ad9245b0fd79b4f383d1ef8531537b03d78ae9b8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96203994"
---
# <a name="_applyjordanwignerzterm_-operation"></a><span data-ttu-id="db3a0-102">_ApplyJordanWignerZTerm_ művelet</span><span class="sxs-lookup"><span data-stu-id="db3a0-102">_ApplyJordanWignerZTerm_ operation</span></span>

<span data-ttu-id="db3a0-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="db3a0-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="db3a0-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="db3a0-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="db3a0-105">Alkalmazza az idő-evolúciót az a által leírt Z kifejezéssel `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="db3a0-105">Applies time-evolution by a Z term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerZTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="db3a0-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="db3a0-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="db3a0-107">kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="db3a0-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="db3a0-108">`GeneratorIndex` egy Z kifejezést jelképez.</span><span class="sxs-lookup"><span data-stu-id="db3a0-108">`GeneratorIndex` representing a Z term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="db3a0-109">stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="db3a0-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="db3a0-110">Az idő időbeli alakulása.</span><span class="sxs-lookup"><span data-stu-id="db3a0-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="db3a0-111">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="db3a0-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="db3a0-112">A Hamilton qubits.</span><span class="sxs-lookup"><span data-stu-id="db3a0-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="db3a0-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="db3a0-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

