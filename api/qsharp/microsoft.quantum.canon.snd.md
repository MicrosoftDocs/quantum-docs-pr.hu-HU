---
uid: Microsoft.Quantum.Canon.Snd
title: Snd-függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: 11786fa195de12a7f2e4f2edb00ac0bc1071dd5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98852152"
---
# <a name="snd-function"></a>Snd-függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy pár után a a második elemet adja vissza.

```qsharp
function Snd<'T, 'U> (pair : ('T, 'U)) : 'U
```


## <a name="input"></a>Bevitel

### <a name="pair--tu"></a>pár: ('T, ' U)

Két elemet tartalmazó rekord.



## <a name="output--u"></a>Kimenet: U

A második eleme `pair` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A pár első tagjának típusa.
### <a name="u"></a>' U

A pár második tagjának típusa.