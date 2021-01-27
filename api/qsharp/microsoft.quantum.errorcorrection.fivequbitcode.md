---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 540dcf1eafa7449f386676a9a3c9562a4d4bf29c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853140"
---
# <a name="fivequbitcode-function"></a>FiveQubitCode függvény

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy QECC értéket ad vissza, amely a ⟦ 5, 1, 3 ⟧ és a dekódert, valamint a helyi szindrómás mérését jelöli.

```qsharp
function FiveQubitCode () : Microsoft.Quantum.ErrorCorrection.QECC
```


## <a name="output--qecc"></a>Kimenet: [QECC](xref:Microsoft.Quantum.ErrorCorrection.QECC)

Egy kvantum-hibajavítási kód végrehajtását adja vissza egy típus megadásával `QECC` .

## <a name="remarks"></a>Megjegyzések

A kód a következő két dokumentumtól függetlenül található:

- C. H. Bennett, D. alvincenzo, J. A. Smolin és W. K. Wootters, "vegyes állapotú felakadás és kvantum-hibajavítás," leltár. Rev. A, 54 (1996) PP. 3824-3851; https://arxiv.org/abs/quant-ph/9604024 és
- R. Leva, C. Miquel, J. P. Paz és W. H Zurek, "tökéletes kvantum-hibajavítási kód", "leltár. Rev. lett. 77 (1996) PP. 198-201; https://arxiv.org/abs/quant-ph/9602019