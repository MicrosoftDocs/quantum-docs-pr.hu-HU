---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: 158a90bbd0c68406e0a8507ae99fc08fad3b6d19
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193845"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="cfe04-102">OracleToDiscrete függvény</span><span class="sxs-lookup"><span data-stu-id="cfe04-102">OracleToDiscrete function</span></span>

<span data-ttu-id="cfe04-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="cfe04-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="cfe04-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cfe04-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cfe04-105">Egy "Black-Box" Oracle-t jelképező művelet miatt egy diszkrét idejű Oracle-t ad vissza, amely a "fekete doboz" Oracle többször ismétlődik.</span><span class="sxs-lookup"><span data-stu-id="cfe04-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="cfe04-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="cfe04-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a><span data-ttu-id="cfe04-107">blackBoxOracle: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="cfe04-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="cfe04-108">A exponentiated művelet.</span><span class="sxs-lookup"><span data-stu-id="cfe04-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="cfe04-109">Kimenet: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="cfe04-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="cfe04-110">Részben alkalmazott művelet a különálló Oracle-t jelképező "fekete doboz" Oracle esetében</span><span class="sxs-lookup"><span data-stu-id="cfe04-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>