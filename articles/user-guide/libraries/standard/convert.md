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
# <a name="type-conversions"></a><span data-ttu-id="3678e-103">Típus konverziója</span><span class="sxs-lookup"><span data-stu-id="3678e-103">Type Conversions</span></span> #

<span data-ttu-id="3678e-104">A Q # egy **határozottan gépelt** nyelv.</span><span class="sxs-lookup"><span data-stu-id="3678e-104">Q# is a **strongly-typed** language.</span></span>
<span data-ttu-id="3678e-105">Különösen a Q # nem végez implicit módon különböző típusok között.</span><span class="sxs-lookup"><span data-stu-id="3678e-105">In particular, Q# does not implicitly cast between distinct types.</span></span> <span data-ttu-id="3678e-106">Például `1 + 2.0` nem érvényes Q # kifejezés.</span><span class="sxs-lookup"><span data-stu-id="3678e-106">For instance, `1 + 2.0` is not a valid Q# expression.</span></span>
<span data-ttu-id="3678e-107">A Q # Ehelyett számos különböző típusú átalakítási függvényt biztosít egy adott típus új értékeinek létrehozásához.</span><span class="sxs-lookup"><span data-stu-id="3678e-107">Rather, Q# provides a variety of type conversion functions for constructing new values of a given type.</span></span>

<span data-ttu-id="3678e-108">A <xref:microsoft.quantum.core.length> kimeneti típusa például a kimenet `Int` , ezért a kimenetét először át kell alakítani, mielőtt egy `Double` lebegőpontos kifejezés részeként lehessen használni.</span><span class="sxs-lookup"><span data-stu-id="3678e-108">For example, <xref:microsoft.quantum.core.length> has an output type of `Int`, so its output must first be converted to a `Double` before it can be used as a part of a floating-point expression.</span></span>
<span data-ttu-id="3678e-109">Ezt a következő függvény használatával teheti meg <xref:microsoft.quantum.convert.intasdouble> :</span><span class="sxs-lookup"><span data-stu-id="3678e-109">This can be done using the <xref:microsoft.quantum.convert.intasdouble> function:</span></span>

```qsharp
open Microsoft.Quantum.Convert as Convert;

function HalfLength<'T>(arr : 'T[]) : Double {
    return Convert.IntAsDouble(Length(arr)) / 2.0;
}
```

<span data-ttu-id="3678e-110">A <xref:microsoft.quantum.convert> névtér általános típus-átalakítási funkciókat biztosít az alapszintű beépített típusok (például:,,, és) használatához `Int` `Double` `BigInt` `Result` `Bool` .</span><span class="sxs-lookup"><span data-stu-id="3678e-110">The <xref:microsoft.quantum.convert> namespace provides common type conversion functions for working with the basic built-in types, such as `Int`, `Double`, `BigInt`, `Result`, and `Bool`:</span></span>

```qsharp
let bool = Convert.ResultAsBool(One);        // true
let big = Convert.IntAsBigInt(271);          // 271L
let indices = Convert.RangeAsIntArray(0..4); // [0, 1, 2, 3, 4]
```

<span data-ttu-id="3678e-111">A <xref:microsoft.quantum.convert> névtér további egzotikus konverziókat is biztosít, például a `FunctionAsOperation` függvényeket `'T -> 'U` új műveletekre alakítja át `'T => 'U` .</span><span class="sxs-lookup"><span data-stu-id="3678e-111">The <xref:microsoft.quantum.convert> namespace also provides some more exotic conversions, such as `FunctionAsOperation`, which converts functions `'T -> 'U` into new operations `'T => 'U`.</span></span>

<span data-ttu-id="3678e-112">Végül a Q # standard Library számos felhasználó által definiált típust biztosít, például a <xref:microsoft.quantum.math.complex> és a <xref:microsoft.quantum.arithmetic.littleendian> .</span><span class="sxs-lookup"><span data-stu-id="3678e-112">Finally, the Q# standard library provides a number of user-defined types such as <xref:microsoft.quantum.math.complex> and <xref:microsoft.quantum.arithmetic.littleendian>.</span></span>
<span data-ttu-id="3678e-113">Ezen típusok mellett a standard könyvtár a következő funkciókat nyújtja <xref:microsoft.quantum.arithmetic.bigendianaslittleendian> :</span><span class="sxs-lookup"><span data-stu-id="3678e-113">Along with these types, the standard library provides functions such as <xref:microsoft.quantum.arithmetic.bigendianaslittleendian>:</span></span>

```Q#
open Microsoft.Quantum.Arithmetic as Arithmetic;

let register = Arithmetic.BigEndian(qubits);
IncrementByInteger(Arithmetic.BigEndianAsLittleEndian(register));
```
