---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerBlockEncodingGeneratorSystem
title: JordanWignerBlockEncodingGeneratorSystem függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerBlockEncodingGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.
ms.openlocfilehash: 49b2a7703a8419d81f44f795cbb38b9560152c46
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214891"
---
# <a name="jordanwignerblockencodinggeneratorsystem-function"></a><span data-ttu-id="f566e-102">JordanWignerBlockEncodingGeneratorSystem függvény</span><span class="sxs-lookup"><span data-stu-id="f566e-102">JordanWignerBlockEncodingGeneratorSystem function</span></span>

<span data-ttu-id="f566e-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="f566e-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="f566e-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="f566e-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="f566e-105">A által ismertetett Hamilton `JWOptimizedHTerms` `GeneratorSystem` a Pauli kifejezésben kifejezett értékre alakítja át `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="f566e-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.</span></span>

```qsharp
function JordanWignerBlockEncodingGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="f566e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f566e-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="f566e-107">adatkezelés: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="f566e-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="f566e-108">A Hamilton leírása `JWOptimizedHTerms` formátumban.</span><span class="sxs-lookup"><span data-stu-id="f566e-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="f566e-109">Kimenet: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="f566e-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="f566e-110">A Hamilton megjelenítése mint `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="f566e-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>