---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliGenIdx
title: _ZZTermToPauliGenIdx függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliGenIdx
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: 01f4ebf4f2acc0fd76ae101e0c511cd70b03fada
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214959"
---
# <a name="_zztermtopauligenidx-function"></a><span data-ttu-id="4d79b-102">_ZZTermToPauliGenIdx függvény</span><span class="sxs-lookup"><span data-stu-id="4d79b-102">_ZZTermToPauliGenIdx function</span></span>

<span data-ttu-id="4d79b-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="4d79b-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="4d79b-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="4d79b-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="4d79b-105">A ZZ kifejezést leíró GeneratorIndex alakítja át a (z) "GeneratorIndex []" kifejezésre, Paulis alapján.</span><span class="sxs-lookup"><span data-stu-id="4d79b-105">Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZZTermToPauliGenIdx (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.GeneratorIndex[]
```


## <a name="input"></a><span data-ttu-id="4d79b-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="4d79b-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="4d79b-107">kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="4d79b-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="4d79b-108">`GeneratorIndex` a ZZ-kifejezést jelölő kifejezés.</span><span class="sxs-lookup"><span data-stu-id="4d79b-108">`GeneratorIndex` representing a ZZ term.</span></span>



## <a name="output--generatorindex"></a><span data-ttu-id="4d79b-109">Kimenet: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span><span class="sxs-lookup"><span data-stu-id="4d79b-109">Output : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)[]</span></span>

<span data-ttu-id="4d79b-110">"GeneratorIndex []" a ZZ kifejezést Pauli-kifejezésként kifejezve.</span><span class="sxs-lookup"><span data-stu-id="4d79b-110">'GeneratorIndex[]' expressing ZZ term as Pauli terms.</span></span>