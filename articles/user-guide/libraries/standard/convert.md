---
title: 'Írja be a konverziókat a :::no-loc(Q#)::: standard könyvtárakba'
description: 'Ismerje meg az általános és a felhasználó által definiált típusú átalakítási funkciókat a :::no-loc(Q#)::: standard könyvtárakban.'
author: cgranade
uid: microsoft.quantum.libraries.convert
ms.author: chgranad
ms.topic: article
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 9ec3a2ecd2aa59a10a7033e7b3067eb147ce4035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691099"
---
# <a name="type-conversions"></a><span data-ttu-id="2e969-103">Típus konverziója</span><span class="sxs-lookup"><span data-stu-id="2e969-103">Type Conversions</span></span> #

<span data-ttu-id="2e969-104">:::no-loc(Q#)::: egy **erősen gépelt** nyelv.</span><span class="sxs-lookup"><span data-stu-id="2e969-104">:::no-loc(Q#)::: is a **strongly-typed** language.</span></span>
<span data-ttu-id="2e969-105">A nem :::no-loc(Q#)::: implicit módon a különböző típusok között történik.</span><span class="sxs-lookup"><span data-stu-id="2e969-105">In particular, :::no-loc(Q#)::: does not implicitly cast between distinct types.</span></span> <span data-ttu-id="2e969-106">Például `1 + 2.0` nem érvényes :::no-loc(Q#)::: kifejezés.</span><span class="sxs-lookup"><span data-stu-id="2e969-106">For instance, `1 + 2.0` is not a valid :::no-loc(Q#)::: expression.</span></span>
<span data-ttu-id="2e969-107">Ehelyett :::no-loc(Q#)::: számos különböző típusú átalakítási függvényt biztosít egy adott típus új értékeinek létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="2e969-107">Rather, :::no-loc(Q#)::: provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="2e969-108">A <xref:Microsoft.Quantum.Core.Length> kimeneti típusa például a kimenet `Int` , ezért a kimenetét először át kell alakítani, mielőtt egy `Double` lebegőpontos kifejezés részeként lehessen használni.</span><span class="sxs-lookup"><span data-stu-id="2e969-108">For example, <xref:Microsoft.Quantum.Core.Length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="2e969-109">Ezt a következő függvény használatával teheti meg <xref:Microsoft.Quantum.Convert.IntAsDouble> :</span><span class="sxs-lookup"><span data-stu-id="2e969-109">This can be done using the <xref:Microsoft.Quantum.Convert.IntAsDouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="2e969-110">A <xref:Microsoft.Quantum.Convert> névtér általános típus-átalakítási funkciókat biztosít az alapszintű beépített típusok (például:,,, és) használatához `Int` `Double` `BigInt` `Result` `Bool` .</span><span class="sxs-lookup"><span data-stu-id="2e969-110">The <xref:Microsoft.Quantum.Convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="2e969-111">A <xref:Microsoft.Quantum.Convert> névtér további egzotikus konverziókat is biztosít, például a `FunctionAsOperation` függvényeket `'T -> 'U` új műveletekre alakítja át `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="2e969-111">The <xref:Microsoft.Quantum.Convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="2e969-112">Végül a :::no-loc(Q#)::: standard könyvtár számos felhasználó által definiált típust biztosít, például a <xref:Microsoft.Quantum.Math.Complex> és a <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .</span><span class="sxs-lookup"><span data-stu-id="2e969-112">Finally, the :::no-loc(Q#)::: standard library provides a number of user-defined types such as <xref:Microsoft.Quantum.Math.Complex> and <xref:Microsoft.Quantum.Arithmetic.LittleEndian>.</span></span>
<span data-ttu-id="2e969-113">Ezen típusok mellett a standard könyvtár a következő funkciókat nyújtja <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :</span><span class="sxs-lookup"><span data-stu-id="2e969-113">Along with these types, the standard library provides functions such as <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian>:</span></span>

```:::no-loc(Q#):::
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
