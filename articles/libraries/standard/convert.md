---
title: 'Típus konverziók a Q # standard könyvtárakban'
description: 'Az általános és a felhasználó által definiált típusú átalakítási függvények ismertetése a Q # standard kódtárakban.'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: e941d7e3d76459546861410e91a03d7315183867
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907800"
---
# <a name="type-conversions"></a>Típus konverziója #

A Q # egy **határozottan gépelt** nyelv.
Különösen a Q # nem végez implicit módon különböző típusok között. Például `1 + 2.0` nem érvényes Q # kifejezés.
A Q # Ehelyett számos különböző típusú átalakítási függvényt biztosít egy adott típus új értékeinek létrehozásához.

Például <xref:microsoft.quantum.core.length> `Int`kimeneti típusa van, ezért a kimenetét először egy `Double`ra kell konvertálni, mielőtt egy lebegőpontos kifejezés részeként lehessen használni.
Ezt a <xref:microsoft.quantum.convert.intasdouble> függvény használatával teheti meg:

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

A <xref:microsoft.quantum.convert> névtér általános típus-átalakítási funkciókat biztosít az alapszintű beépített típusok (például `Int`, `Double`, `BigInt`, `Result`és `Bool`) használatához:

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

A <xref:microsoft.quantum.convert> névtér további egzotikus konverziókat is biztosít, például a `FunctionAsOperation`, amely a függvényeket `'T -> 'U` új műveleti `'T => 'U`alakítja át.

Végül a Q # standard Library számos felhasználó által definiált típust tartalmaz, például <xref:microsoft.quantum.math.complex> és <xref:microsoft.quantum.arithmetic.littleendian>.
Ezen típusok mellett a szabványos függvénytár olyan funkciókat is biztosít, mint például a <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
