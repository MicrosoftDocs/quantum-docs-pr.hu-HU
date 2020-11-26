---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 5fac832ef5b7d7be2d85675a32f45e66312f66c8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200370"
---
# <a name="steanecoderecoveryx-function"></a>SteaneCodeRecoveryX függvény

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


A ⟦ 7, 1, 3 ⟧ Steane kvantum-kód stabilizátor csoportjába tartozó X-részhez tartozó dekóder.

```qsharp
function SteaneCodeRecoveryX (syndrome : Microsoft.Quantum.ErrorCorrection.Syndrome) : Pauli[]
```


## <a name="input"></a>Bevitel

### <a name="syndrome--syndrome"></a>szindróma: [szindróma](xref:Microsoft.Quantum.ErrorCorrection.Syndrome)

A stabilizátor X-részének mérésével kapott tünetegyüttes-tömb.



## <a name="output--pauli"></a>Kimenet: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Egy olyan Pauli-műveletből álló tömb, amely a kódolt kvantum-rendszerre alkalmazva kijavította a megfelelő hibát `syndrome` .

## <a name="remarks"></a>Megjegyzések

A kiválasztott dekóder a ⟦ 7, 1, 3 ⟧ Steane kód CSS Code tulajdonságát használja, azaz az X hibákat és a Z hibákat külön-külön kijavította. A kód egy tulajdonsága az, hogy az alkalmazni kívánt X, vagy Z érték az X, a z szindróma 3 bites kódolása, ha egész számnak számít.

## <a name="references"></a>Hivatkozások

- D. Gottesman, "stabilizátor-kódok és kvantum-hibák javítása" Ph.D. tézis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryFns](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)