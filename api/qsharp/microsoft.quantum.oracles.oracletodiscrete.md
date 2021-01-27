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
# <a name="oracletodiscrete-function"></a>OracleToDiscrete függvény

Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy "Black-Box" Oracle-t jelképező művelet miatt egy diszkrét idejű Oracle-t ad vissza, amely a "fekete doboz" Oracle többször ismétlődik.

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>Bevitel

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a>blackBoxOracle: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit)  az Adj + CTL

A exponentiated művelet.



## <a name="output--discreteoracle"></a>Kimenet: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Részben alkalmazott művelet a különálló Oracle-t jelképező "fekete doboz" Oracle esetében

## <a name="example"></a>Példa

`OracleToDiscrete(U)(3, target)``U(target)`háromszor ismétlődik.