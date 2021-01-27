---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: d39fcd6b2987b3a4f69df13fa83b69a199d6eddb
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840890"
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

