---
title: 'Q # standard könyvtárak – típus konverziója | Microsoft Docs'
description: 'Q # standard könyvtárak – típus konverziók'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 4716f0d9562229f08ef6f0f5f80961f793de4c5c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2019
ms.locfileid: "73184474"
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
