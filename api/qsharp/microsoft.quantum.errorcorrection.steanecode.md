---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: ea36320fff1f0c24426e2fcead976ef051d6699f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712184"
---
# <a name="steanecode-function"></a>SteaneCode függvény

Névtér: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Csomag [](https://nuget.org/packages/)


Egy CSS-értéket ad vissza, amely a ⟦ 7, 1, 3 ⟧ Steane és a dekódert a helyi szindrómás mérésével adja meg.

```qsharp
function SteaneCode () : Microsoft.Quantum.ErrorCorrection.CSS
```


## <a name="output--css"></a>Kimenet: [CSS](xref:Microsoft.Quantum.ErrorCorrection.CSS)

Egy CSS típusú objektum, amely összegyűjti az összes releváns adatot a ⟦ 7, 1, 3 ⟧ Steane kód kódolásának és hibajavításának elvégzéséhez.

## <a name="remarks"></a>Megjegyzések

Ez a kód a következő dokumentumban található:

- A. Steane, "több részecske-interferencia és kvantum-hibajavítás", proc. Roy. SoC. Lond. A452 (1996) PP. 2551; https://arxiv.org/abs/quant-ph/9601029.