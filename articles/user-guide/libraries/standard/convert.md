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
ms.openlocfilehash: aa8a1ad624067906998d2735c7a95174a163ce97
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: hu-HU
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835604"
---
# <a name="type-conversions"></a><span data-ttu-id="a008f-103">Típus konverziója</span><span class="sxs-lookup"><span data-stu-id="a008f-103">Type Conversions</span></span> #

<span data-ttu-id="a008f-104">Q# egy **erősen gépelt** nyelv.</span><span class="sxs-lookup"><span data-stu-id="a008f-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="a008f-105">A nem Q# implicit módon a különböző típusok között történik.</span><span class="sxs-lookup"><span data-stu-id="a008f-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="a008f-106">Például `1 + 2.0` nem érvényes Q# kifejezés.</span><span class="sxs-lookup"><span data-stu-id="a008f-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="a008f-107">Ehelyett Q# számos különböző típusú átalakítási függvényt biztosít egy adott típus új értékeinek létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="a008f-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="a008f-108">A <xref:microsoft.quantum.core.length> kimeneti típusa például a kimenet `Int` , ezért a kimenetét először át kell alakítani, mielőtt egy `Double` lebegőpontos kifejezés részeként lehessen használni.</span><span class="sxs-lookup"><span data-stu-id="a008f-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="a008f-109">Ezt a következő függvény használatával teheti meg <xref:microsoft.quantum.convert.intasdouble> :</span><span class="sxs-lookup"><span data-stu-id="a008f-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="a008f-110">A <xref:microsoft.quantum.convert> névtér általános típus-átalakítási funkciókat biztosít az alapszintű beépített típusok (például:,,, és) használatához `Int` `Double` `BigInt` `Result` `Bool` .</span><span class="sxs-lookup"><span data-stu-id="a008f-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="a008f-111">A <xref:microsoft.quantum.convert> névtér további egzotikus konverziókat is biztosít, például a `FunctionAsOperation` függvényeket `'T -> 'U` új műveletekre alakítja át `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="a008f-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="a008f-112">Végül a Q# standard könyvtár számos felhasználó által definiált típust biztosít, például a <xref:microsoft.quantum.math.complex> és a <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="a008f-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="a008f-113">Ezen típusok mellett a standard könyvtár a következő funkciókat nyújtja <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :</span><span class="sxs-lookup"><span data-stu-id="a008f-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
