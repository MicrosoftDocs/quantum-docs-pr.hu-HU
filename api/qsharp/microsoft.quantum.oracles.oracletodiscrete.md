---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: ab59cdf0ab05092a9d4e7856b7808b13df655571
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842539"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="17b0e-102">OracleToDiscrete függvény</span><span class="sxs-lookup"><span data-stu-id="17b0e-102">OracleToDiscrete function</span></span>

<span data-ttu-id="17b0e-103">Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="17b0e-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="17b0e-104">Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="17b0e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="17b0e-105">Egy "Black-Box" Oracle-t jelképező művelet miatt egy diszkrét idejű Oracle-t ad vissza, amely a "fekete doboz" Oracle többször ismétlődik.</span><span class="sxs-lookup"><span data-stu-id="17b0e-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="17b0e-106">Bevitel</span><span class="sxs-lookup"><span data-stu-id="17b0e-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a><span data-ttu-id="17b0e-107">blackBoxOracle: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="17b0e-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="17b0e-108">A exponentiated művelet.</span><span class="sxs-lookup"><span data-stu-id="17b0e-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="17b0e-109">Kimenet: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="17b0e-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="17b0e-110">Részben alkalmazott művelet a különálló Oracle-t jelképező "fekete doboz" Oracle esetében</span><span class="sxs-lookup"><span data-stu-id="17b0e-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>

## <a name="example"></a><span data-ttu-id="17b0e-111">Példa</span><span class="sxs-lookup"><span data-stu-id="17b0e-111">Example</span></span>

<span data-ttu-id="17b0e-112">`OracleToDiscrete(U)(3, target)``U(target)`háromszor ismétlődik.</span><span class="sxs-lookup"><span data-stu-id="17b0e-112">`OracleToDiscrete(U)(3, target)` is equivalent to `U(target)` repeated three times.</span></span>