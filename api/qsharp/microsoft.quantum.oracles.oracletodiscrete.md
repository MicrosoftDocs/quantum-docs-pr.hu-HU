---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: d26d57c587f24e7f74102c12753bcddb00fd8a9d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724243"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="f1693-102">OracleToDiscrete függvény</span><span class="sxs-lookup"><span data-stu-id="f1693-102">OracleToDiscrete function</span></span>

<span data-ttu-id="f1693-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="f1693-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="f1693-104">Csomag [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f1693-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f1693-105">Egy "Black-Box" Oracle-t jelképező művelet miatt egy diszkrét idejű Oracle-t ad vissza, amely a "fekete doboz" Oracle többször ismétlődik.</span><span class="sxs-lookup"><span data-stu-id="f1693-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="f1693-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="f1693-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a><span data-ttu-id="f1693-107">blackBoxOracle: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="f1693-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="f1693-108">A exponentiated művelet.</span><span class="sxs-lookup"><span data-stu-id="f1693-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="f1693-109">Kimenet: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="f1693-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="f1693-110">Részben alkalmazott művelet a különálló Oracle-t jelképező "fekete doboz" Oracle esetében</span><span class="sxs-lookup"><span data-stu-id="f1693-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>