---
title: 'Típus konverziók a Q # standard könyvtárakban'
description: 'Az általános és a felhasználó által definiált típusú átalakítási függvények ismertetése a Q # standard kódtárakban.'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: e941d7e3d76459546861410e91a03d7315183867
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275007"
---
# <a name="type-conversions"></a>Típus konverziója #

A Q # egy **határozottan gépelt** nyelv.
Különösen a Q # nem végez implicit módon különböző típusok között. Például `1 + 2.0` nem érvényes Q # kifejezés.
A Q # Ehelyett számos különböző típusú átalakítási függvényt biztosít egy adott típus új értékeinek létrehozásához.

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

Végül a Q # standard Library számos felhasználó által definiált típust biztosít, például a <xref:microsoft.quantum.math.complex> és a <xref:microsoft.quantum.arithmetic.littleendian> .
Ezen típusok mellett a standard könyvtár a következő funkciókat nyújtja <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
