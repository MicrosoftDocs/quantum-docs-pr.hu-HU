---
uid: Microsoft.Quantum.Logical.Conditioned
title: Feltételes függvény
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Conditioned
qsharp.summary: Returns one of two values, depending on the value of a Boolean condition.
ms.openlocfilehash: 8aabe8b018129ddee3b934c207d0a62e59fb6f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720785"
---
# <a name="conditioned-function"></a>Feltételes függvény

Névtér: [Microsoft. Quantum. Logic](xref:Microsoft.Quantum.Logical)

Csomag [](https://nuget.org/packages/)


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

```Q#
let x = condition ? ifTrue | ifFalse;
let x = Conditioned(condition, ifTrue, ifFalse);
```