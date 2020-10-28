---
uid: Microsoft.Quantum.Oracles.ObliviousOracleFromDeterministicStateOracle
title: ObliviousOracleFromDeterministicStateOracle függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracleFromDeterministicStateOracle
qsharp.summary: Combines the oracles `DeterministicStateOracle` and `ObliviousOracle`.
ms.openlocfilehash: 9e18776ad4d6adf0068213117c6d1d8ed5c5f126
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722226"
---
# <a name="obliviousoraclefromdeterministicstateoracle-function"></a>ObliviousOracleFromDeterministicStateOracle függvény

Névtér: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Csomag [](https://nuget.org/packages/)


Egyesíti az Oracle `DeterministicStateOracle` -ket és a-t `ObliviousOracle` .

```qsharp
function ObliviousOracleFromDeterministicStateOracle (ancillaOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle) : Microsoft.Quantum.Oracles.ObliviousOracle
```


## <a name="input"></a>Bevitel

### <a name="ancillaoracle--deterministicstateoracle"></a>ancillaOracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Olyan állapot-előkészítési Oracle $A $, amely a (z `DeterministicStateOracle` ) $a $ regiszterben működik.


### <a name="signaloracle--obliviousoracle"></a>signalOracle: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Egy Oracle $U $ típusú, amely `ObliviousOracle` a register $a, s $ címen közösen működik.



## <a name="output--obliviousoracle"></a>Kimenet: [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

Egy Oracle $O = UA $ típusú `ObliviousOracle` .

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft. Quantum. Oracles. ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)