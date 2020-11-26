---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerGeneratorSystem
title: JordanWignerGeneratorSystem függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 0f6719cfac1c50cd55da30e57b0b5c5214813f24
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214721"
---
# <a name="jordanwignergeneratorsystem-function"></a><span data-ttu-id="ac7cc-102">JordanWignerGeneratorSystem függvény</span><span class="sxs-lookup"><span data-stu-id="ac7cc-102">JordanWignerGeneratorSystem function</span></span>

<span data-ttu-id="ac7cc-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="ac7cc-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="ac7cc-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="ac7cc-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="ac7cc-105">A által ismertetett Hamilton alakítja át `JWOptimizedHTerms` `GeneratorSystem` az `GeneratorIndex` ebben a fájlban meghatározott egyezményben kifejezett kifejezéssel.</span><span class="sxs-lookup"><span data-stu-id="ac7cc-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.</span></span>

```qsharp
function JordanWignerGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a><span data-ttu-id="ac7cc-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="ac7cc-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="ac7cc-107">adatkezelés: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="ac7cc-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="ac7cc-108">A Hamilton leírása `JWOptimizedHTerms` formátumban.</span><span class="sxs-lookup"><span data-stu-id="ac7cc-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--generatorsystem"></a><span data-ttu-id="ac7cc-109">Kimenet: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="ac7cc-109">Output : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)</span></span>

<span data-ttu-id="ac7cc-110">A Hamilton megjelenítése mint `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="ac7cc-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>