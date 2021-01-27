---
uid: Microsoft.Quantum.Logical.Conditioned
title: Feltételes függvény
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: ea3b8eba960acceb6540978c6fccd9f796b0f67d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817285"
---
# <a name="conditioned-function"></a>Feltételes függvény

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Egy logikai feltétel értékétől függően két érték egyikét adja vissza.

```qsharp
function Conditioned<'T> (condition : Bool, ifTrue : 'T, ifFalse : 'T) : 'T
```


## <a name="input"></a>Bevitel

### <a name="condition--bool"></a>feltétel: [bool](xref:microsoft.quantum.lang-ref.bool)

A visszaadott bemenet szabályozására szolgáló feltétel.


### <a name="iftrue--t"></a>ifTrue: nem

Az értékeként visszaadott érték `condition` `true` .


### <a name="iffalse--t"></a>ifFalse: nem

Az értékeként visszaadott érték `condition` `false` .



## <a name="output--t"></a>Kimenet: nem

`ifTrue` Ha `condition` van `true` , és `ifFalse` egyéb módon.

## <a name="type-parameters"></a>Típusparaméterek

### <a name="t"></a>Nem



## <a name="remarks"></a>Megjegyzések

Az `?|` operátortól eltérően ez a függvény nem rövidzárlat, így mindkét bemenet teljes mértékben ki van értékelve.

Akár rövid összekapcsolási viselkedés, a következők egyenértékűek:

```qsharp
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```