---
uid: Microsoft.Quantum.Simulation.PauliCoefficientFromGenIdx
title: PauliCoefficientFromGenIdx függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: PauliCoefficientFromGenIdx
qsharp.summary: Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.
ms.openlocfilehash: eb4f7a538e85ade4b095aa3ea5eab4448eda2491
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847996"
---
# <a name="paulicoefficientfromgenidx-function"></a><span data-ttu-id="0618b-102">PauliCoefficientFromGenIdx függvény</span><span class="sxs-lookup"><span data-stu-id="0618b-102">PauliCoefficientFromGenIdx function</span></span>

<span data-ttu-id="0618b-103">Névtér: [Microsoft. Quantum. szimulációs](xref:Microsoft.Quantum.Simulation)</span><span class="sxs-lookup"><span data-stu-id="0618b-103">Namespace: [Microsoft.Quantum.Simulation](xref:Microsoft.Quantum.Simulation)</span></span>

<span data-ttu-id="0618b-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0618b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0618b-105">Kibontja az a által leírt Pauli-kifejezés hatékonyságát `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="0618b-105">Extracts the coefficient of a Pauli term described by a `GeneratorIndex`.</span></span>

```qsharp
function PauliCoefficientFromGenIdx (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Double
```


## <a name="input"></a><span data-ttu-id="0618b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="0618b-106">Input</span></span>

### <a name="generatorindex--generatorindex"></a><span data-ttu-id="0618b-107">generatorIndex: [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="0618b-107">generatorIndex : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="0618b-108">`GeneratorIndex` egy Pauli-kifejezést kódoló típus.</span><span class="sxs-lookup"><span data-stu-id="0618b-108">`GeneratorIndex` type that encodes a Pauli term.</span></span>



## <a name="output--double"></a><span data-ttu-id="0618b-109">Kimenet: [dupla](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0618b-109">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0618b-110">Az a pont által leírt feltételek együtthatója `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="0618b-110">The coefficient of the term described by a `GeneratorIndex`.</span></span>