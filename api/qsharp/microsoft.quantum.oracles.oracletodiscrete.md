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
# <a name="oracletodiscrete-function"></a>OracleToDiscrete függvény

Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Csomag [](https://nuget.org/packages/)


Egy "Black-Box" Oracle-t jelképező művelet miatt egy diszkrét idejű Oracle-t ad vissza, amely a "fekete doboz" Oracle többször ismétlődik.

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>Bevitel

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a>blackBoxOracle: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [egység](xref:microsoft.quantum.lang-ref.unit) Adj + CTL

A exponentiated művelet.



## <a name="output--discreteoracle"></a>Kimenet: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Részben alkalmazott művelet a különálló Oracle-t jelképező "fekete doboz" Oracle esetében