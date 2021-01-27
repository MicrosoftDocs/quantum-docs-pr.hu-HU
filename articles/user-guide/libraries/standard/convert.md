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
# <a name="type-conversions"></a><span data-ttu-id="f2381-103">Típus konverziója</span><span class="sxs-lookup"><span data-stu-id="f2381-103">Type Conversions</span></span> #

<span data-ttu-id="f2381-104">Q# egy **erősen gépelt** nyelv.</span><span class="sxs-lookup"><span data-stu-id="f2381-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="f2381-105">A nem Q# implicit módon a különböző típusok között történik.</span><span class="sxs-lookup"><span data-stu-id="f2381-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="f2381-106">Például `1 + 2.0` nem érvényes Q# kifejezés.</span><span class="sxs-lookup"><span data-stu-id="f2381-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="f2381-107">Ehelyett Q# számos különböző típusú átalakítási függvényt biztosít egy adott típus új értékeinek létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="f2381-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="f2381-108">A <xref:Microsoft.Quantum.Core.Length> kimeneti típusa például a kimenet `Int` , ezért a kimenetét először át kell alakítani, mielőtt egy `Double` lebegőpontos kifejezés részeként lehessen használni.</span><span class="sxs-lookup"><span data-stu-id="f2381-108">For example, <xref:Microsoft.Quantum.Core.Length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="f2381-109">Ezt a következő függvény használatával teheti meg <xref:Microsoft.Quantum.Convert.IntAsDouble> :</span><span class="sxs-lookup"><span data-stu-id="f2381-109">This can be done using the <xref:Microsoft.Quantum.Convert.IntAsDouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="f2381-110">A <xref:Microsoft.Quantum.Convert> névtér általános típus-átalakítási funkciókat biztosít az alapszintű beépített típusok (például:,,, és) használatához `Int` `Double` `BigInt` `Result` `Bool` .</span><span class="sxs-lookup"><span data-stu-id="f2381-110">The <xref:Microsoft.Quantum.Convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="f2381-111">A <xref:Microsoft.Quantum.Convert> névtér további egzotikus konverziókat is biztosít, például a `FunctionAsOperation` függvényeket `'T -> 'U` új műveletekre alakítja át `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="f2381-111">The <xref:Microsoft.Quantum.Convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="f2381-112">Végül a Q# standard könyvtár számos felhasználó által definiált típust biztosít, például a <xref:Microsoft.Quantum.Math.Complex> és a <xref:Microsoft.Quantum.Arithmetic.LittleEndian> .</span><span class="sxs-lookup"><span data-stu-id="f2381-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:Microsoft.Quantum.Math.Complex> and <xref:Microsoft.Quantum.Arithmetic.LittleEndian>.</span></span>
<span data-ttu-id="f2381-113">Ezen típusok mellett a standard könyvtár a következő funkciókat nyújtja <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian> :</span><span class="sxs-lookup"><span data-stu-id="f2381-113">Along with these types, the standard library provides functions such as <xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian>:</span></span>

```qsharp
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
