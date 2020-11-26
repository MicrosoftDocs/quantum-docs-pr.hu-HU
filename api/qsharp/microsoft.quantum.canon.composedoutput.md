---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput függvény
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 7e361a62679ab93e9a0ebc04fa52be193805c78d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207462"
---
# <a name="composedoutput-function"></a>ComposedOutput függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


`inner`Egy adott bemenethez tartozó összeállítás kimenetét adja vissza `outer` .

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a>Bevitel

### <a name="outer--u---v"></a>külső: "U->" V




### <a name="inner--t---u"></a>belső: nem > U




### <a name="target--t"></a>cél: nem





## <a name="output--v"></a>Kimenet: "V



## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem


### <a name="u"></a>' U


### <a name="v"></a>"V

