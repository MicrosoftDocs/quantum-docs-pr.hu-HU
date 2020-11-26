---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: PauliCoefficientFromGenIdx függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: 59ddadabb5c77cdb0d2e3620a09433992e85f663
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225057"
---
# <a name="paulicoefficientfromgenidx-function"></a><span data-ttu-id="e5966-102">PauliCoefficientFromGenIdx függvény</span><span class="sxs-lookup"><span data-stu-id="e5966-102">PauliCoefficientFromGenIdx function</span></span>

<span data-ttu-id="e5966-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="e5966-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="e5966-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e5966-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e5966-105">Kibontja az a által leírt Pauli-kifejezés hatékonyságát `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="e5966-105">Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a><span data-ttu-id="e5966-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="e5966-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="e5966-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="e5966-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="e5966-108">`GeneratorIndex` egy Pauli-kifejezést kódoló típus.</span><span class="sxs-lookup"><span data-stu-id="e5966-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--double"></a><span data-ttu-id="e5966-109">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e5966-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="e5966-110">Az a pont által leírt feltételek együtthatója `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="e5966-110">The coefficient of the term described by a `GeneratorIndex`.</span></span>