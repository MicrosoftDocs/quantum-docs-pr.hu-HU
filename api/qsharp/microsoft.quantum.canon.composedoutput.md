---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716483"
---
# <a name="composedoutput-function"></a>ComposedOutput függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


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

