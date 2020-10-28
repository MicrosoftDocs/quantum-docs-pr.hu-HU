---
uid: Microsoft.Quantum.Targeting.RequiresCapability
title: RequiresCapability-felhasználó által definiált típus
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Targeting
qsharp.name: RequiresCapability
qsharp.summary: Compiler-recognized attribute used to mark a callable with the runtime capabilities it requires.
ms.openlocfilehash: 63b1952d402f1bcb81a8f9d0afc3cdf7aa7e5ed8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725138"
---
# <a name="requirescapability-user-defined-type"></a>RequiresCapability-felhasználó által definiált típus

Névtér: [Microsoft. Quantum. Targeting](xref:Microsoft.Quantum.Targeting)

Csomag [](https://nuget.org/packages/)


Fordító által felismert attribútum, amely egy meghívót jelöl meg a szükséges futtatókörnyezeti képességekkel.

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype RequiresCapability = (Level : String, Reason : String);
```



## <a name="named-items"></a>Megnevezett elemek

### <a name="level--string"></a>Szint: [sztring](xref:microsoft.quantum.lang-ref.string)

A meghíváshoz szükséges futásidejű képességi szint neve.
### <a name="reason--string"></a>Ok: [karakterlánc](xref:microsoft.quantum.lang-ref.string)

Annak leírása, hogy a hívó miért igényli ezt a futásidejű képességet.

## <a name="remarks"></a>Megjegyzések

Ezt az attribútumot a fordító automatikusan hozzáadja a callables, kivéve, ha az attribútum egy példánya már létezik a meghívóhoz. Nem használható, kivéve olyan ritka esetekben, amikor a fordító nem következteti ki a szükséges képességet.

Az alábbi lista a képességek szintjének neveinek listáját mutatja be a kapacitás növelése vagy a csökkenő korlátozások érdekében:

## `"BasicQuantumFunctionality"`

A mérési eredmények nem hasonlíthatók össze az egyenlőséghez.

## `"BasicMeasurementFeedback"`

A mérési eredmények összehasonlítható a műveletekben szereplő if-utasítás feltételes kifejezésekben szereplő egyenlőséggel. Egy Eredménytől függő if-utasítás blokkban nem szerepelhetnek a blokkon kívül deklarált, változtatható változókhoz tartozó set utasítások, vagy a Return utasítások.

## `"FullComputation"`

Nincs futásidejű korlátozás. Bármely Q # program végrehajtható.