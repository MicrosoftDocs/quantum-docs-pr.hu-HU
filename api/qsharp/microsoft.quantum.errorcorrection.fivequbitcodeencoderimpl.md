---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeEncoderImpl
title: FiveQubitCodeEncoderImpl művelet
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeEncoderImpl
qsharp.summary: Private operation used to implement both the 5 qubit encoder and decoder.
ms.openlocfilehash: 29b0f47ddffeae3ed4dfda4084304427418e02fd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712338"
---
# <a name="fivequbitcodeencoderimpl-operation"></a>FiveQubitCodeEncoderImpl művelet

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag [](https://nuget.org/packages/)


Az 5 qubit kódoló és a dekóder megvalósításához használt magánhálózati művelet.

```qsharp
operation FiveQubitCodeEncoderImpl (data : Qubit[], scratch : Qubit[]) : Unit
```


## <a name="input"></a>Bevitel

### <a name="data--qubit"></a>adatkezelés: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

egy 1 qubit tartalmazó tömb, amely a bemeneti qubit.


### <a name="scratch--qubit"></a>Scratch: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

egy 4 qubits rendelkező tömb, amely redundancia hozzáadását.



## <a name="output--unit"></a>Kimenet: [egység](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Megjegyzések

A kiválasztott kódoló az V. Kliuchnikov és A D. Maslov, a Clifford-áramkörök optimalizálása, a Leltárnapló. Rev. Leltárnapló. a 88, 052307 (2013). https://arxiv.org/abs/1305.08104b. ábra), és összesen 11 kaput igényel.