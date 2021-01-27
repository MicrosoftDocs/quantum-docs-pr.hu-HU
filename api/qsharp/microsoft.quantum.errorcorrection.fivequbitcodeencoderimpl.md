---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: FiveQubitCodeEncoderImpl művelet
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 0a40d9674c011567b2fa9c838f31a0ee115e4268
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826085"
---
# <a name="fivequbitcodeencoderimpl-operation"></a>FiveQubitCodeEncoderImpl művelet

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Az 5 qubit kódoló és a dekóder megvalósításához használt magánhálózati művelet.

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit is Adj
```


## <a name="input"></a>Bevitel

### <a name="data--qubit"></a>adatkezelés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

egy 1 qubit tartalmazó tömb, amely a bemeneti qubit.


### <a name="scratch--qubit"></a>Scratch: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

egy 4 qubits rendelkező tömb, amely redundancia hozzáadását.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A kiválasztott kódoló az V. Kliuchnikov és A D. Maslov, a Clifford-áramkörök optimalizálása, a Leltárnapló. Rev. Leltárnapló. a 88, 052307 (2013). https://arxiv.org/abs/1305.08104b. ábra), és összesen 11 kaput igényel.