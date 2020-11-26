---
uid: Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBlockEncodingGeneratorSystem
title: OptimizedBlockEncodingGeneratorSystem függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: OptimizedBlockEncodingGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.
ms.openlocfilehash: 1d59c7655b5534465717dd816848011527df4a42
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214585"
---
# <a name="optimizedblockencodinggeneratorsystem-function"></a><span data-ttu-id="1bacb-102">OptimizedBlockEncodingGeneratorSystem függvény</span><span class="sxs-lookup"><span data-stu-id="1bacb-102">OptimizedBlockEncodingGeneratorSystem function</span></span>

<span data-ttu-id="1bacb-103">Névtér: [Microsoft. Quantum. kémia. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span><span class="sxs-lookup"><span data-stu-id="1bacb-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)</span></span>

<span data-ttu-id="1bacb-104">Csomag: [Microsoft. Quantum. kémia](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="1bacb-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="1bacb-105">A által ismertetett Hamilton `JWOptimizedHTerms` `GeneratorSystem` a Pauli kifejezésben kifejezett értékre alakítja át `GeneratorIndex` .</span><span class="sxs-lookup"><span data-stu-id="1bacb-105">Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the Pauli `GeneratorIndex`.</span></span>

```qsharp
function OptimizedBlockEncodingGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem
```


## <a name="input"></a><span data-ttu-id="1bacb-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="1bacb-106">Input</span></span>

### <a name="data--jwoptimizedhterms"></a><span data-ttu-id="1bacb-107">adatkezelés: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span><span class="sxs-lookup"><span data-stu-id="1bacb-107">data : [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)</span></span>

<span data-ttu-id="1bacb-108">A Hamilton leírása `JWOptimizedHTerms` formátumban.</span><span class="sxs-lookup"><span data-stu-id="1bacb-108">Description of Hamiltonian in `JWOptimizedHTerms` format.</span></span>



## <a name="output--optimizedbegeneratorsystem"></a><span data-ttu-id="1bacb-109">Kimenet: [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span><span class="sxs-lookup"><span data-stu-id="1bacb-109">Output : [OptimizedBEGeneratorSystem](xref:Microsoft.Quantum.Chemistry.JordanWigner.OptimizedBEGeneratorSystem)</span></span>

<span data-ttu-id="1bacb-110">A Hamilton megjelenítése mint `GeneratorSystem` .</span><span class="sxs-lookup"><span data-stu-id="1bacb-110">Representation of Hamiltonian as `GeneratorSystem`.</span></span>