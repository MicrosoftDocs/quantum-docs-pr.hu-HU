---
title: Írja be a konverziókat a Q# standard könyvtárakba
description: Ismerje meg az általános és a felhasználó által definiált típusú átalakítási funkciókat a Q# standard könyvtárakban.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2319bf453f5fbf6bd068859ea65562423d3ff4d0
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868513"
---
# <a name="type-conversions"></a>Típus konverziója #

Q#egy **erősen gépelt** nyelv.
A nem Q# implicit módon a különböző típusok között történik. Például `1 + 2.0` nem érvényes Q# kifejezés.
Ehelyett Q# számos különböző típusú átalakítási függvényt biztosít egy adott típus új értékeinek létrehozásához.

A <xref:microsoft.quantum.core.length> kimeneti típusa például a kimenet `Int` , ezért a kimenetét először át kell alakítani, mielőtt egy `Double` lebegőpontos kifejezés részeként lehessen használni.
Ezt a következő függvény használatával teheti meg <xref:microsoft.quantum.convert.intasdouble> :

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

A <xref:microsoft.quantum.convert> névtér általános típus-átalakítási funkciókat biztosít az alapszintű beépített típusok (például:,,, és) használatához `Int` `Double` `BigInt` `Result` `Bool` .

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

A <xref:microsoft.quantum.convert> névtér további egzotikus konverziókat is biztosít, például a `FunctionAsOperation` függvényeket `'T -> 'U` új műveletekre alakítja át `'T => 'U` .

Végül a Q# standard könyvtár számos felhasználó által definiált típust biztosít, például a <xref:microsoft.quantum.math.complex> és a <xref:microsoft.quantum.arithmetic.littleendian> .
Ezen típusok mellett a standard könyvtár a következő funkciókat nyújtja <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
