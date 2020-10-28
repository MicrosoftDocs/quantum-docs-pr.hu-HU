---
title: Írja be a konverziókat a Q# standard könyvtárakba
description: Ismerje meg az általános és a felhasználó által definiált típusú átalakítási funkciókat a Q# standard könyvtárakban.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9ec3a2ecd2aa59a10a7033e7b3067eb147ce4035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691099"
---
# <a name="type-conversions"></a>Típus konverziója #

Q# egy **erősen gépelt** nyelv.
A nem Q# implicit módon a különböző típusok között történik. Például `1 + 2.0` nem érvényes Q# kifejezés.
Ehelyett Q# számos különböző típusú átalakítási függvényt biztosít egy adott típus új értékeinek létrehozásához.

A <xref:Microsoft.Quantum.Core.Length> kimeneti típusa például a kimenet `Int` , ezért a kimenetét először át kell alakítani, mielőtt egy `Double` lebegőpontos kifejezés részeként lehessen használni.
Ezt a következő függvény használatával teheti meg <xref:Microsoft.Quantum.Convert.IntAsDouble> :

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

A <xref:Microsoft.Quantum.Convert> névtér általános típus-átalakítási funkciókat biztosít az alapszintű beépített típusok (például:,,, és) használatához `Int` `Double` `BigInt` `Result` `Bool` .

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

A <xref:Microsoft.Quantum.Convert> névtér további egzotikus konverziókat is biztosít, például a `FunctionAsOperation` függvényeket `'T -> 'U` új műveletekre alakítja át `'T => 'U` .

Végül a Q# standard könyvtár számos felhasználó által definiált típust biztosít, például a <xref:Microsoft.Quantum.Math.Complex> és a <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .
Ezen típusok mellett a standard könyvtár a következő funkciókat nyújtja <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
