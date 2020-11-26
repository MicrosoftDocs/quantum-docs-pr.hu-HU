---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeEncoderImpl
title: SteaneCodeEncoderImpl művelet
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeEncoderImpl
qsharp.summary: Private operation used to implement both the Steane code encoder and decoder.
ms.openlocfilehash: 3a9a1b11ed9255f18135e3717de7e9e1ec891298
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200425"
---
# <a name="steanecodeencoderimpl-operation"></a>SteaneCodeEncoderImpl művelet

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A Steane-kód kódolójának és dekóderének megvalósításához használt magánhálózati művelet.

```qsharp
operation SteaneCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Bevitel

### <a name="data--qubit"></a>adatkezelés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

egy 1 qubit tartalmazó tömb, amely a bemeneti qubit.


### <a name="scratch--qubit"></a>Scratch: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

egy 6 qubits rendelkező tömb, amely redundancia hozzáadását.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)

