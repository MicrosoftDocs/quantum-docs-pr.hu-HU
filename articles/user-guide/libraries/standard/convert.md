---
title: Írja be a konverziókat a Q# standard könyvtárakba
description: Ismerje meg az általános és a felhasználó által definiált típusú átalakítási funkciókat a Q# standard könyvtárakban.
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: conceptual
no-loc:
- Q#
- $$v
ms.openlocfilehash: 67f47339363a52097f342c8ae4e43a8a93d606a8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858025"
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

```qsharp
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
