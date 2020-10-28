---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCode
title: FiveQubitCode függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCode
qsharp.summary: Returns a QECC value representing the ⟦5, 1, 3⟧ code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: 7509de880b1e3ea8964b61e4b3f034ce20b2f202
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712339"
---
# <a name="fivequbitcode-function"></a>FiveQubitCode függvény

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag [](https://nuget.org/packages/)


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