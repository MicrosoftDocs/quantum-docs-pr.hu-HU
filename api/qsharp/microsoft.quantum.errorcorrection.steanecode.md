---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: af3f3ef5088b898bd827ebca00fdc7fcb992f2a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853059"
---
# <a name="steanecode-function"></a>SteaneCode függvény

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy CSS-értéket ad vissza, amely a ⟦ 7, 1, 3 ⟧ Steane és a dekódert a helyi szindrómás mérésével adja meg.

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>Kimenet: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

Egy CSS típusú objektum, amely összegyűjti az összes releváns adatot a ⟦ 7, 1, 3 ⟧ Steane kód kódolásának és hibajavításának elvégzéséhez.

## <a name="remarks"></a>Megjegyzések

Ez a kód a következő dokumentumban található:

- A. Steane, "több részecske-interferencia és kvantum-hibajavítás", proc. Roy. SoC. Lond. A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.