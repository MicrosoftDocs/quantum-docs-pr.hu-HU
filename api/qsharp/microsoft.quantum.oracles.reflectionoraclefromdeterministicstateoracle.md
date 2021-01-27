---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c260bdbcdb2ce53ad602bf84e0d31ef4fec24a79
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842529"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a>ReflectionOracleFromDeterministicStateOracle függvény

Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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