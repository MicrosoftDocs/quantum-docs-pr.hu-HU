---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: 4eed29072cab9e8c106509a6a114c8a071441079
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842501"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a>StateOracleFromDeterministicStateOracle függvény

Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy típusú Oracle `DeterministicStateOracle` -t konvertál `StateOracle` .

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a>Bevitel

### <a name="deterministicstateoracle--deterministicstateoracle"></a>deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Állapot-előkészítési Oracle $A $ típusú `DeterministicStateOracle` .



## <a name="output--stateoracle"></a>Kimenet: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Ugyanez az állapot-előkészítési Oracle $A $, de mostantól típusa `StateOracle` . Vegye figyelembe, hogy a jelölő indexe `StateOracle` egy dummy változó, és nincs hatása.

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft. Quantum. Oracles. StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)