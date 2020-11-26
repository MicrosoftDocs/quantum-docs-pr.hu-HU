---
uid: Microsoft.Quantum.Chemistry.JordanWigner._ZZTermToPauliMajIdx_
title: _ZZTermToPauliMajIdx_ függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: _ZZTermToPauliMajIdx_
qsharp.summary: Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.
ms.openlocfilehash: ca713260da2dd717cb1548ef86b7faa0d1b826aa
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214925"
---
# <a name="_zztermtopaulimajidx_-function"></a><span data-ttu-id="35b81-102">_ZZTermToPauliMajIdx_ függvény</span><span class="sxs-lookup"><span data-stu-id="35b81-102">_ZZTermToPauliMajIdx_ function</span></span>

<span data-ttu-id="35b81-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="35b81-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="35b81-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="35b81-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="35b81-105">A ZZ kifejezést leíró GeneratorIndex alakítja át a (z) "GeneratorIndex []" kifejezésre, Paulis alapján.</span><span class="sxs-lookup"><span data-stu-id="35b81-105">Converts a GeneratorIndex describing a ZZ term to an expression 'GeneratorIndex[]' in terms of Paulis.</span></span>

```qsharp
function _ZZTermToPauliMajIdx_ (term : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex
```


## <a name="input"></a><span data-ttu-id="35b81-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="35b81-106">Input</span></span>

### <a name="term--generatorindex"></a><span data-ttu-id="35b81-107">kifejezés: [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span><span class="sxs-lookup"><span data-stu-id="35b81-107">term : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)</span></span>

<span data-ttu-id="35b81-108">`GeneratorIndex` a ZZ-kifejezést jelölő kifejezés.</span><span class="sxs-lookup"><span data-stu-id="35b81-108">`GeneratorIndex` representing a ZZ term.</span></span>



## <a name="output--optimizedbetermindex"></a><span data-ttu-id="35b81-109">Kimenet: [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span><span class="sxs-lookup"><span data-stu-id="35b81-109">Output : [OptimizedBETermIndex](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBETermIndex)</span></span>

<span data-ttu-id="35b81-110">"GeneratorIndex []" a ZZ kifejezést Pauli-kifejezésként kifejezve.</span><span class="sxs-lookup"><span data-stu-id="35b81-110">'GeneratorIndex[]' expressing ZZ term as Pauli terms.</span></span>