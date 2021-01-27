---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ApplyJordanWignerPQandPQQRTerm_
title: _ApplyJordanWignerPQandPQQRTerm_ művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ApplyJordanWignerPQandPQQRTerm_
qsharp.summary: Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.
ms.openlocfilehash: cd4a63378f4e491217a7bb478a8ea3dcce67bc5a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839567"
---
# <a name="_applyjordanwignerpqandpqqrterm_-operation"></a><span data-ttu-id="6e0ac-102">_ApplyJordanWignerPQandPQQRTerm_ művelet</span><span class="sxs-lookup"><span data-stu-id="6e0ac-102">_ApplyJordanWignerPQandPQQRTerm_ operation</span></span>

<span data-ttu-id="6e0ac-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="6e0ac-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="6e0ac-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6e0ac-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="6e0ac-105">Alkalmazza az idő-evolúciót az a által leírt PQ vagy PQQR kifejezéssel `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="6e0ac-105">Applies time-evolution by a PQ or PQQR term described by a `GeneratorIndex`.</span></span>

```qsharp
operation _ApplyJordanWignerPQandPQQRTerm_ (term : Microsoft.Quantum.Simulation.GeneratorIndex, stepSize : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="6e0ac-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="6e0ac-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="6e0ac-107">kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="6e0ac-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="6e0ac-108">`GeneratorIndex` PQ vagy PQQR kifejezést jelképez.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-108">`GeneratorIndex` representing a PQ or PQQR term.</span></span>


### <a name="stepsize--double"></a><span data-ttu-id="6e0ac-109">stepSize: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6e0ac-109">stepSize : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6e0ac-110">Az idő időbeli alakulása.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-110">Duration of time-evolution.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="6e0ac-111">qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="6e0ac-111">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="6e0ac-112">A Hamilton qubits.</span><span class="sxs-lookup"><span data-stu-id="6e0ac-112">Qubits of Hamiltonian.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6e0ac-113">Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6e0ac-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

