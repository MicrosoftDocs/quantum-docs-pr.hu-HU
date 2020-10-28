---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX
title: SteaneCodeRecoveryX függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCodeRecoveryX
qsharp.summary: Decoder for the X-part of the stabilizer group of the ⟦7, 1, 3⟧ Steane quantum code.
ms.openlocfilehash: 0f6b987ca23bd9ff2076080d60f1ca756b36848e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712129"
---
# <a name="steanecoderecoveryx-function"></a>SteaneCodeRecoveryX függvény

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag [](https://nuget.org/packages/)


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

## <a name="references"></a>Referencia

- D. Gottesman, "stabilizátor-kódok és kvantum-hibák javítása" Ph.D. tézis, Caltech, 1997; https://arxiv.org/abs/quant-ph/9705052

## <a name="see-also"></a>Lásd még:

- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryX](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryX)
- [Microsoft. Quantum. ErrorCorrection. SteaneCodeRecoveryFns](xref:Microsoft.Quantum.ErrorCorrection.SteaneCodeRecoveryFns)