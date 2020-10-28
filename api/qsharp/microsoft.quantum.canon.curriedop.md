---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: 13bc3e195d8a4ba26b726f96e4dc6b83da43c3e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716370"
---
# <a name="curriedop-function"></a>CurriedOp függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag [](https://nuget.org/packages/)


Egy művelet egy két bemenetén lévő, a művelethez tartozó, Currie-beli verzióját adja vissza.

Ez azt eredményezi, hogy a művelet két bemenettel rendelkezik, ez a függvény a curry isomorphism $f (x, y) \equiv f (x) (y) $-t alkalmazza egy olyan bemenet műveletének visszaadására, amely egy bemenet műveletét adja vissza.

```qsharp
function CurriedOp<'T, 'U> (op : (('T, 'U) => Unit)) : ('T -> ('U => Unit))
```


## <a name="input"></a>Bevitel

### <a name="op--tu--unit"></a>op: (nem, ' U) => [egység](xref:microsoft.quantum.lang-ref.unit) 

Olyan művelet, amelynek bemenete egy pár.



## <a name="output--t---u--unit"></a>Kimenet: nem > ' U => [egység](xref:microsoft.quantum.lang-ref.unit) 

Egy olyan művelet, amely egy pár első elemét fogadja, és egy olyan műveletet ad vissza, amely az eredeti művelet bemenetének második elemeként fogadja el.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem

A párokban definiált függvény első összetevőjének típusa.
### <a name="u"></a>' U

A párokban definiált függvény második összetevőjének típusa.

## <a name="remarks"></a>Megjegyzések

A következők egyenértékűek:

```qsharp
op(x, y);

let curried = CurriedOp(op);
let partial = curried(x);
partial(y);
```