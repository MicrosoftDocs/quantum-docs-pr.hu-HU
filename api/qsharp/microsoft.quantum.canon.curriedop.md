---
uid: Microsoft.Quantum.Canon.CurriedOp
title: CurriedOp függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CurriedOp
qsharp.summary: >-
  Returns a curried version of an operation on two inputs.

  That is, given an operation with two inputs, this function applies Curry's isomorphism $f(x, y) \equiv f(x)(y)$ to return an operation of one input which returns an operation of one input.
ms.openlocfilehash: f811347d65a6460690163e9df631979c906bd89f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840768"
---
# <a name="curriedop-function"></a>CurriedOp függvény

Névtér: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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