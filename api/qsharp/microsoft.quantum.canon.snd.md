---
uid: Microsoft.Quantum.Canon.Snd
title: Snd-függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Snd
qsharp.summary: Given a pair, returns its second element.
ms.openlocfilehash: c935a2bc9e3f5ab32669feae2bfc0f2ebf57e744
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96205320"
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