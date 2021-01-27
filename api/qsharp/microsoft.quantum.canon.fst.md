---
uid: Microsoft.Quantum.Canon.Fst
title: FST függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Fst
qsharp.summary: Given a pair, returns its first element.
ms.openlocfilehash: cd5746358c8323f8d2dbca44965fa5dbac0a84c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840512"
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