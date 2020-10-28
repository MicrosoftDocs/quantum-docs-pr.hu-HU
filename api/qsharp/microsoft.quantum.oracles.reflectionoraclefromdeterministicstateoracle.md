---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c2d37216aebcdc5243d0f1d6ec9db261cc9bd0c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722184"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a>ReflectionOracleFromDeterministicStateOracle függvény

Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Csomag [](https://nuget.org/packages/)


Egy Oracle-ből származó adott állapottal kapcsolatos reflexiót hoz létre.

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a>Leírás

Mivel a determinisztikus állapot-előkészítési Oracle egy egységes Matrix $O $-t képvisel, a függvény eredménye egy Oracle, amely az Oracle $O $ által előkészített \ket{\psi} $ állapotot tükrözi. vagyis a $ \ket{\psi} $ állapotot, amely $O \ket {0} = \ket{\psi} $.

## <a name="input"></a>Bevitel

### <a name="oracle--deterministicstateoracle"></a>Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Egy Oracle, amely előkészíti a $ \ket{\psi} $ állapotú példányokat.



## <a name="output--reflectionoracle"></a>Kimenet: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Egy Oracle, amely a $ \ket{\psi} $ állapotot tükrözi.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft. Quantum. Oracles. ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)