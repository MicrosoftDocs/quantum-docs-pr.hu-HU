---
uid: Microsoft.Quantum.ErrorCorrection.DecodeFromSteaneCode
title: DecodeFromSteaneCode művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeFromSteaneCode
qsharp.summary: An inverse encoding operation that maps an unencoded quantum register to an encoded quantum register under the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 54e47b65ed7a89c8ff9026126a9542d3d7ba15cc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827393"
---
# <a name="decodefromsteanecode-operation"></a>DecodeFromSteaneCode művelet

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Inverz kódolási művelet, amely egy nem kódolt kvantum-regisztrációt képez le egy kódolt kvantum-regiszterbe a ⟦ 7, 1, 3 ⟧ Steane kvantum-kódjában.

```qsharp
operation DecodeFromSteaneCode (logicalRegister : Microsoft.Quantum.ErrorCorrection.LogicalRegister) : (Qubit[], Qubit[])
```


## <a name="input"></a>Bevitel

### <a name="logicalregister--logicalregister"></a>logicalRegister: [logicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)

A kódolt 5 qubit kód logikai állapotát jelképező qubits tömbje.



## <a name="output--qubitqubit"></a>Kimenet: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[])

Az 1. hosszúságú qubit tömb, amely az első paraméterben szereplő, nem kódolt állapotot jelöli, a második paraméter kiegészítő qubits együtt.

## <a name="remarks"></a>Megjegyzések

A kiválasztott dekóder a ⟦ 7, 1, 3 ⟧ Steane kód CSS Code tulajdonságát használja, azaz az X hibákat és a Z hibákat külön-külön kijavította. A kód egy tulajdonsága az, hogy az alkalmazni kívánt X, vagy Z érték az X, a z szindróma 3 bites kódolása, ha egész számnak számít.

## <a name="references"></a>Hivatkozások

- D. Gottesman, "stabilizátor-kódok és kvantum-hibák javítása" Ph.D. tézis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. ErrorCorrection. SteaneCodeEncoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoder)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeDecoder](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeDecoder)
- [Microsoft. Quantum. ErrorCorrection. LogicalRegister](xref:Microsoft.Quantum.ErrorCorrection.LogicalRegister)