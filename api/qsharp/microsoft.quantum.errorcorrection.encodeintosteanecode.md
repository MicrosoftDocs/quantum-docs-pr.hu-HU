---
uid: Microsoft.Quantum.ErrorCorrection.EncodeIntoSteaneCode
title: EncodeIntoSteaneCode művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeIntoSteaneCode
qsharp.summary: An encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 2f65423a17dafadd1f9f10a07335150dfc8bf886
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826203"
---
# <a name="encodeintosteanecode-operation"></a>EncodeIntoSteaneCode művelet

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Kódolási művelet, amely egy nem kódolt kvantum-regisztrációt képez le egy kódolt kvantum-regiszterbe a ⟦ 7, 1, 3 ⟧ Steane kvantum-kódjában.

```qsharp
operation EncodeIntoSteaneCode (physRegister : Qubit[], auxQubits : Qubit[]) : Microsoft.Quantum.ErrorCorrection.LogicalRegister
```


## <a name="input"></a>Bevitel

### <a name="physregister--qubit"></a>physRegister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Olyan qubit-regisztráció, amely a nem kódolt kvantum-állapotot tartalmazza


### <a name="auxqubits--qubit"></a>auxQubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Olyan qubit-regisztráció, amely kezdetben nulla, és amely a kvantum-rendszerbe kerül, így a kódolási művelet elvégezhető.



## <a name="output--logicalregister"></a>Kimenet: [LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

Az állapotot a Steane-kódoló alkalmazása után betöltő kvantum-regisztráció

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)