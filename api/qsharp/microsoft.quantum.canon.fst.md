---
uid: Microsoft.Quantum.Canon.Fst
title: FST függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: 634f11881a054df7fe79d889832ea6bd80a7394f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206935"
---
# <a name="fst-function"></a>FST függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy pár után visszaadja az első elemét.

```qsharp
function Fst<'T, 'U> (pair : ('T, 'U)) : 'T
```


## <a name="input"></a>Bevitel

### <a name="pair--tu"></a>pár: ('T, ' U)

Két elemet tartalmazó rekord.



## <a name="output--t"></a>Kimenet: nem

A első eleme `pair` .

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A pár első tagjának típusa.
### <a name="u"></a>' U

A pár második tagjának típusa.