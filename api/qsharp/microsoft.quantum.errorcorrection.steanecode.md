---
uid: Microsoft.Quantum.ErrorCorrection.SteaneCode
title: SteaneCode függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: SteaneCode
qsharp.summary: Returns a CSS value representing the ⟦7, 1, 3⟧ Steane code encoder and decoder with in-place syndrome measurement.
ms.openlocfilehash: b981c82acfa82cd58d82666703d4bb95ac5df280
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96200475"
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