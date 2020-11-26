---
uid: Microsoft.Quantum.Simulation.PauliStringFromGenIdx
title: PauliStringFromGenIdx függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliStringFromGenIdx
qsharp.summary: Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: a937dc648c5de5a5f6de7da996448af497b92185
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230310"
---
# <a name="paulistringfromgenidx-function"></a><span data-ttu-id="67429-102">PauliStringFromGenIdx függvény</span><span class="sxs-lookup"><span data-stu-id="67429-102">PauliStringFromGenIdx function</span></span>

<span data-ttu-id="67429-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="67429-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="67429-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="67429-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="67429-105">Kibontja a Pauli-karakterláncot és annak qubit-indexeit egy, a által leírt Pauli-kifejezésből `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="67429-105">Extracts the Pauli string and its qubit indices of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliStringFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : (Pauli[], Int[])
```


## <a name="input"></a><span data-ttu-id="67429-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="67429-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="67429-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="67429-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="67429-108">`GeneratorIndex` egy Pauli-kifejezést kódoló típus.</span><span class="sxs-lookup"><span data-stu-id="67429-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--pauliint"></a><span data-ttu-id="67429-109">Kimenet: ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[int](xref:microsoft.quantum.lang-ref.int)[])</span><span class="sxs-lookup"><span data-stu-id="67429-109">Output : ([Pauli](xref:microsoft.quantum.lang-ref.pauli)[],[Int](xref:microsoft.quantum.lang-ref.int)[])</span></span>

<span data-ttu-id="67429-110">Az a kifejezés, amely az a és az általa a qubits által leírt kifejezést írja le `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="67429-110">The Pauli string of the term described by a `GeneratorIndex`, and indices to the qubits it acts on.</span></span>